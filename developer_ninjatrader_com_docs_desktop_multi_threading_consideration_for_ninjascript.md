## [Multi-Threading Overview](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#multi-threading-overview)

With the introduction of multi-threading in NinjaTrader special considerations should be made when programming your NinjaScript objects. Multi-threading basically allows NinjaTrader to take advantage of multi-core CPUs commonplace in modern computing to do multiple tasks at the same time. While this has many advantages for multi-tasking, it can cause new types of issues you may have not needed to consider before. This page was designed to serve as a high-level overview of some of the most common scenarios that can arise due to multi-threading, but should not be considered an exhaustive list.

## [Using A Dispatcher](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#using-a-dispatcher)

Depending on your CPU configuration, the NinjaTrader application will usually consist of multiple main UI threads, where various features like Charts or NinjaScript objects run, along with a number of background worker threads where events such as market data updates will be distributed throughout the product. In principle, an object can only access information related to objects that exist on the same thread. It is possible (and quite likely), that the thread which a NinjaScript object is running will not be the same thread as the event which is calling the object. In cases where you need to access objects on the UI from a NinjaScript objects calling event thread, a **dispatcher** can be used.

## Note

As a best practice, you should always make sure to use [Dispatcher.InvokeAsync()](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher.invokeasync(v=vs.110).aspx) to ensure your action is done asynchronously to any internal NinjaTrader actions. Calling the synchronous Dispatcher.Invoke() method can potentially result in a deadlock scenarios as your script is loaded.

```jsx-150469391 csharp

if (State == State.Historical)
{
   if (ChartControl != null)
   {
     // add some text to the UserControlCollection through the ChartControls dispatcher
     ChartControl.Dispatcher.InvokeAsync(new Action(() => {
         UserControlCollection.Add(new System.Windows.Controls.TextBlock {
           Text = "\nAdded by the ChartControl Dispatcher."
         });
     }));
   }
}

```

## [Thread Access](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#thread-access)

Since market data is distributed across the entire application by a randomly assigned UI thread, there is no guarantee that your object will be running on the same event thread that is calling the object. Therefore it is recommend that you call [Dispatcher.CheckAccess()](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher.checkaccess(v=vs.110).aspx) in order to test if you truly need to dispatch the requested action.

```jsx-150469391 csharp

// check if the current object is already on the calling thread
if (Dispatcher.CheckAccess())
{
   // execute action directly
   action(args);
}
// otherwise run the action from the thread that created the object
else
{
   // dispatch action to calling thread
   Dispatcher.InvokeAsync(action, args);
}

```

## [Cross Thread Exceptions](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#cross-thread-exceptions)

When accessing objects included on the UI, you may receive the following error if you attempt to access a certain property/method from the wrong thread:

"Error on calling 'OnBarUpdate' method on bar 0: You are accessing an object which resides on another thread. I.E. creating your own **Brush** without calling .Freeze(), or trying to access a UI control from the wrong thread without using a **Dispatcher**"

This error can be avoided by invoking the **Dispatcher** used on the appropriate UI thread.

## [Access Violation Exception](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#access-violation-exception)

Should you be using custom resources like text files, static members, etc. it is important to protect your resources from concurrent access. If NinjaTrader tried to use the resource at the same time you would run into errors similar to this one:

8/20/2010 12:14:29 PM\|3\|128\|Error on calling 'OnBarUpdate' method for strategy 'SampleStrategy/1740b50bfe5d4bd896b0533725622400': The process cannot access the file 'c:\\sample.txt' because it is being used by another process.

```jsx-150469391 csharp

private object lockObj = new object();

private void WriteFile()
{
   // lock a generic object to ensure only one thread is accessing the following code block at a time
   lock (lockObj)
   {
       string filePath = @"C:\sample.txt";
       using (System.IO.FileStream file = new System.IO.FileStream(filePath, FileMode.Append, FileAccess.Write, FileShare.None))
       {
           // write something to the file...

           // be sure to flush the buffer so everything is written to the file.
           file.Flush();

           // The "using" block implicitly closes the FileStream object,
           // giving other threads access to the file
       }
   }
}

```

## [Multi-threaded consideration for Order, Execution and Position objects](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#multi-threaded-consideration-for-order,-execution-and-position-objects)

These considerations apply to the [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate), [OnExecutionUpdate()](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate) and [OnPositionUpdate()](https://developer.ninjatrader.com/docs/desktop/onpositionupdate) handlers, where both the actual 'core' objects are passed by reference and updating method value parameters are provided. Exemplary the [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) is discussed in below.

- [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) method guarantees that you will see each order state change in sequence
- The "order" method parameter represents the core order object updated by NinjaTrader
- The supplementary method parameters provide an updating value representing each order change in sequence. Think of this as the relevant information on the order at the time the state changed.
- Since the "order" method parameter represents the current order object state, it is possible for the updating values of that object to be out of sync with the correspond method parameters during a particular order update event.

As an example, the NinjaTrader core may have received "Working" and then "PartFilled" order state change events back from the broker API on thread "B". At some point in time (milliseconds later) the NinjaTrader core will take these events and trigger the **OnOrderUpdate()** method in the strategy on thread "A". Thus, when the strategy receives the first "Working" state for an order, the **orderState** method parameter will reflect the "Working" state although the actual **order.OrderState** is really in a state of "Part Filled". You would see that current value truly reflected in the core **Order** object method parameter or any order objects returned in any of the order methods such as **EnterLong()**. Of course, the **OnOrderUpdate()** method parameters will eventually receive the event for "PartFilled" state in the sequence the events were received.

Considering the concept above, if you are unsure if you should be using the core order object value vs the updating method parameter value, ask yourself if you are truly looking for the most current order state, or the sequence of order states:

- For the most current order state, use the core **order** object property (e.g., **order.OrderState**, **order.LimitPrice**, **order.StopPrice**, etc)
- For the sequence of order states, use the updating method parameter value (e.g., **orderState**, **limitPrice**, **stopPrice**, etc)

## [Multi-Threading Overview](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#multi-threading-overview)

With the introduction of multi-threading in NinjaTrader special considerations should be made when programming your NinjaScript objects. Multi-threading basically allows NinjaTrader to take advantage of multi-core CPUs commonplace in modern computing to do multiple tasks at the same time. While this has many advantages for multi-tasking, it can cause new types of issues you may have not needed to consider before. This page was designed to serve as a high-level overview of some of the most common scenarios that can arise due to multi-threading, but should not be considered an exhaustive list.

## [Using A Dispatcher](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#using-a-dispatcher)

Depending on your CPU configuration, the NinjaTrader application will usually consist of multiple main UI threads, where various features like Charts or NinjaScript objects run, along with a number of background worker threads where events such as market data updates will be distributed throughout the product. In principle, an object can only access information related to objects that exist on the same thread. It is possible (and quite likely), that the thread which a NinjaScript object is running will not be the same thread as the event which is calling the object. In cases where you need to access objects on the UI from a NinjaScript objects calling event thread, a **dispatcher** can be used.

## Note

As a best practice, you should always make sure to use [Dispatcher.InvokeAsync()](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher.invokeasync(v=vs.110).aspx) to ensure your action is done asynchronously to any internal NinjaTrader actions. Calling the synchronous Dispatcher.Invoke() method can potentially result in a deadlock scenarios as your script is loaded.

```jsx-150469391 csharp

if (State == State.Historical)
{
   if (ChartControl != null)
   {
     // add some text to the UserControlCollection through the ChartControls dispatcher
     ChartControl.Dispatcher.InvokeAsync(new Action(() => {
         UserControlCollection.Add(new System.Windows.Controls.TextBlock {
           Text = "\nAdded by the ChartControl Dispatcher."
         });
     }));
   }
}

```

## [Thread Access](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#thread-access)

Since market data is distributed across the entire application by a randomly assigned UI thread, there is no guarantee that your object will be running on the same event thread that is calling the object. Therefore it is recommend that you call [Dispatcher.CheckAccess()](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher.checkaccess(v=vs.110).aspx) in order to test if you truly need to dispatch the requested action.

```jsx-150469391 csharp

// check if the current object is already on the calling thread
if (Dispatcher.CheckAccess())
{
   // execute action directly
   action(args);
}
// otherwise run the action from the thread that created the object
else
{
   // dispatch action to calling thread
   Dispatcher.InvokeAsync(action, args);
}

```

## [Cross Thread Exceptions](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#cross-thread-exceptions)

When accessing objects included on the UI, you may receive the following error if you attempt to access a certain property/method from the wrong thread:

"Error on calling 'OnBarUpdate' method on bar 0: You are accessing an object which resides on another thread. I.E. creating your own **Brush** without calling .Freeze(), or trying to access a UI control from the wrong thread without using a **Dispatcher**"

This error can be avoided by invoking the **Dispatcher** used on the appropriate UI thread.

## [Access Violation Exception](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#access-violation-exception)

Should you be using custom resources like text files, static members, etc. it is important to protect your resources from concurrent access. If NinjaTrader tried to use the resource at the same time you would run into errors similar to this one:

8/20/2010 12:14:29 PM\|3\|128\|Error on calling 'OnBarUpdate' method for strategy 'SampleStrategy/1740b50bfe5d4bd896b0533725622400': The process cannot access the file 'c:\\sample.txt' because it is being used by another process.

```jsx-150469391 csharp

private object lockObj = new object();

private void WriteFile()
{
   // lock a generic object to ensure only one thread is accessing the following code block at a time
   lock (lockObj)
   {
       string filePath = @"C:\sample.txt";
       using (System.IO.FileStream file = new System.IO.FileStream(filePath, FileMode.Append, FileAccess.Write, FileShare.None))
       {
           // write something to the file...

           // be sure to flush the buffer so everything is written to the file.
           file.Flush();

           // The "using" block implicitly closes the FileStream object,
           // giving other threads access to the file
       }
   }
}

```

## [Multi-threaded consideration for Order, Execution and Position objects](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript\#multi-threaded-consideration-for-order,-execution-and-position-objects)

These considerations apply to the [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate), [OnExecutionUpdate()](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate) and [OnPositionUpdate()](https://developer.ninjatrader.com/docs/desktop/onpositionupdate) handlers, where both the actual 'core' objects are passed by reference and updating method value parameters are provided. Exemplary the [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) is discussed in below.

- [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) method guarantees that you will see each order state change in sequence
- The "order" method parameter represents the core order object updated by NinjaTrader
- The supplementary method parameters provide an updating value representing each order change in sequence. Think of this as the relevant information on the order at the time the state changed.
- Since the "order" method parameter represents the current order object state, it is possible for the updating values of that object to be out of sync with the correspond method parameters during a particular order update event.

As an example, the NinjaTrader core may have received "Working" and then "PartFilled" order state change events back from the broker API on thread "B". At some point in time (milliseconds later) the NinjaTrader core will take these events and trigger the **OnOrderUpdate()** method in the strategy on thread "A". Thus, when the strategy receives the first "Working" state for an order, the **orderState** method parameter will reflect the "Working" state although the actual **order.OrderState** is really in a state of "Part Filled". You would see that current value truly reflected in the core **Order** object method parameter or any order objects returned in any of the order methods such as **EnterLong()**. Of course, the **OnOrderUpdate()** method parameters will eventually receive the event for "PartFilled" state in the sequence the events were received.

Considering the concept above, if you are unsure if you should be using the core order object value vs the updating method parameter value, ask yourself if you are truly looking for the most current order state, or the sequence of order states:

- For the most current order state, use the core **order** object property (e.g., **order.OrderState**, **order.LimitPrice**, **order.StopPrice**, etc)
- For the sequence of order states, use the updating method parameter value (e.g., **orderState**, **limitPrice**, **stopPrice**, etc)