There are some best practices to be aware of when developing **NinjaScript** classes. The following tables present a non-exhaustive list of considerations to keep in mind when designing and implementing your code.

## Note

- NinjaTrader is multi-threaded and event driven. Always assume that any of the methods you implement in NinjaScript could be called from another thread.

## [State management practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#state-management-practices)

### Managing Resources

- The **OnStateChange()** method is called anytime there has been a change of **State** and can be used to help you setup, manage, and destroy several types of resources. Where these values are setup is highly dependent on the kind of resource you are using. The section below will cover how to manage various resources throughout different states.

### Setting Default UI Property Grid values

- Reserve **State.SetDefaults** for defaulting any public properties you wish to have exposed on the UI property grid. You should also use this **State** for setting default desired **NinjaScript** property behavior which can be overridden from the property grid (e.g. **Calculate**, **IsOverlay**, etc.). For Plots and Lines you wish to configure, **AddPlot()**, **AddLine()** should also have their default values set during this **State**.

| Why |
| --- |
| Public values of the **NinjaScript** object in **SetDefaults** are pushed to the UI property grid for an opportunity to change settings of your object. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // these are the values that show up as default on the UI
   if (State == State.SetDefaults)
   {
     Calculate = Calculate.OnPriceChange;
     IsOverlay = false;

     Period = 50;

     AddPlot(Brushes.Blue, "Plot Value");
     AddLine(Brushes.Gray, 100, "Threshold");
   }

```

For public properties you do NOT wish exposed to the UI property grid, set the **Browsable** attribute to false:

```jsx-150469391 csharp
// Best practice
[Browsable(false)] // prevents from showing up on the UI property grid
public int Communicator { get; set;

```

On indicators, properties you wish to set from other objects, set the **NinjaScriptPropertyAttribute**:

```jsx-150469391 csharp
// Best practice
[NinjaScriptProperty] // can now call **MyIndicator**(20) from another object
public int Period { get; set; }

```

The default behavior is to serialize any public properties and fields to a Workspace or Template file when saving. However, not all objects can be serialized - or you may wish to exclude a property from being saved and restored. For these scenarios, set the **XmlIgnore** attribute to the property:

```jsx-150469391 csharp
// Best practice
[XmlIgnore] // removes from serialization
public Brush DownBrush
{ get; set; }

```

As a best practice as well, your **NinjaScript** should not have any public fields, since those would get serialized as well - which means their state would be persisted, which in turn could lead to unexpected outcomes.

## Note

- See the [Working with Brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes) section of the Help Guide for information on properly serializing brushes.

### Calculating run-time object values

Do not attempt to do advanced calculations or try to access object references in **State.SetDefaults**. This **State** should be kept as lean as possible, and any calculation logic should be delayed until at least **State.Configure**.

| Why |
| --- |
| Your object will be called in situations you may not be expecting. You can read more about this subject on [Understanding the life cycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of). |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       // logic could take longer than desired as the list of indicator names is populated
       for (int i = 0; i <= array.length; i++)
           DoWork(i);

       // possible null reference exception since **TickSize** is not set yet
       Period = 5 * TickSize;
   }

```

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // Complex operations should be delayed to >= State.Configure
   if (State == State.Configure)
   {
       for (int i = 0; i <= array.length; i++)
           DoWork(i);
   }

   // information related to market data is not available until at least State.DataLoaded
   else if (State == State.DataLoaded)
   {
       Period = 5 * TickSize;
   }
}

```

### Setting class level variables

Do not set variables at the class level unless they are constant. You should delay setting or resetting variables until the **State** has reached **State.Configure**. You can use **const** keyword to differentiate values which do not change from variables which do change.

| Why |
| --- |
| Waiting to set up and define resources until the object has been configured ensures that values not set up and declared prematurely. |

```jsx-150469391 csharp
// Best practice
// value is always 5, it can be made constant and declared at the class level
private const int multiplier = 5;

// these values can change, may be better to delay setting until State.Configure
private int counter;
private List<int> myList;

protected override void OnStateChange()
{
   if (State == State.Configure)
   {
       counter = 0;
       myList = new List<int>();
   }

```

### Resetting class level variables for Strategy Analyzer Optimization

To take advantage of performance optimizations, developers may need to reset class level variables in the strategy otherwise unexpected results can occur.

| Why |
| --- |
| When optimizing a strategy, instances may or may not be recycled depending on the strategy **IsInstantiatedOnEachOptimizationIteration** setting. |

```jsx-150469391 csharp
// Best practice
// examples of fields which need to be reset
private double myDouble;
private bool myBool;
private DateTime myDateTime;
private Order myOrderObject;
private Brush myBrushObject;
private Array myIntArray;
private List<object> myList;
private SMA mySMAIndicator;
private Series<double> mySeries;

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       // disabled to take advantage of performance gains
       // However any strategy state that would be mutable after State.SetDefaults needed to be reset for the next run.
       IsInstantiatedOnEachOptimizationIteration = false;
   }
   else if (State == State.Configure)
   {
       // Since these values are not dependent on bars, they can be reset as early as State.Configure
       myDouble = double.MinValue;
       myBool = false;
       myDateTime = DateTime.MinValue;
       myOrderObject = null;
       myBrushObject = null;

       if (myIntArray != null)
           Array.Clear(myIntArray, 0, myIntArray.Length);
       else
           myIntArray = new int[20];

       if (myList != null)
           myList.Clear();
       else
           myList = new List<object>();
   }

   else if (State == State.DataLoaded)
   {
       // Since these values do are dependent on bars, they should only reset during State.DataLoaded
       mySMAIndicator = SMA(14);
       mySeries = new Series<double>(this);
   }

```

### Accessing properties related to market data

Do not attempt to access objects related to instrument market data until the **State** has reached **State.DataLoaded**.

| Why |
| --- |
| Waiting to access objects that depend on market data until **DataLoaded** prevents access errors in all scenarios. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       // these objects and their related members are not available until State.DataLoaded
       Print(Bars.Count);
       Print(Instrument.FullName);
       Print(BarsPeriod.BarsPeriodType);
       Print(TradingHours.TimeZon;
       Print(Input);
   }
}

```

## Note

- All additional data series must be added in **State.Configure** (this includes series that any hosted script potentially needs as well - [more info](https://developer.ninjatrader.com/docs/desktop/adddataseries)). Since objects such as **Instrument**, **BarsPeriod**, **TradingHours**, etc. are NOT guaranteed to be available until **State.DataLoaded**, you cannot reliably use the primary instrument properties as arguments in **AddDataSeries()**. Attempting to add a data series dynamically is NOT guaranteed and therefore should be avoided. In some cases, you may be able to use a **BarsRequest()** to obtain market data for other instruments and intervals.

### Setting up resources that rely on market data

For objects which depend on market data, delay their construction until the **State** has reached **State.DataLoaded**.

| Why |
| --- |
| Waiting to construct objects that depend on market data until **DataLoaded** ensures that their underlying input contains significant values in all scenarios. |

```jsx-150469391 csharp
// Best practice
// these resources depend on bars, wait until State.DataLoaded to instantiated
private EMA myEMA;
private Series<double> mySeries;
private SessionIterator mySessionIterator;

protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       myEMA = EMA(20);
       mySeries = new Series<double>(this);
       mySessionIterator = new SessionIterator(Bars);
   }

```

### Accessing element on the UI

For objects which exist on the UI (e.g., **ChartControl**, **ChartPanel**, **ChartBars**, **NTWindow**, etc.) wait until the **State** has reached **State.Historical**. This practice is correct for both reading properties or should you wish to add custom elements to the existing UI.

| Why |
| --- |
| **NinjaTrader** UI related objects are not guaranteed to be available until historical data processing has started. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // wait until at least State.Historical
   if (State == State.Historical)
   {
       // and double check UI object is not null before accessing
       if (ChartControl != null)
       {
           Print(ChartControl.Properties.ChartBackground);
       }
   }
}

```

### Transitioning order references from historical to real-time

When dealing with strategy based orders which have transitioned from historical to real-time, you will need to ensure that locally stored order references are also updated.

| Why |
| --- |
| As the core order object updates, **NinjaTrader** has no specific way to update your locally stored order references. You can read more about this subject on the Advanced Order Handling topic: [Transitioning order references from historical to live](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling). |

```jsx-150469391 csharp
// Best practice
private Order entryOrder = null;

protected override void OnBarUpdate()
{
   if (entryOrder == null && Close[0] > Open[0])
       entryOrder = EnterLongLimit("myEntryOrder", Low[0]);
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
   // One time only, as we transition from historical
   // Convert any old historical order object references to the live order submitted to the real-time account
   if (entryOrder != null && entryOrder.IsBacktestOrder && State == State.Realtime)
       entryOrder = GetRealtimeOrder(entryOrder);

   // Null entryOrder if filled or cancelled. We do not use the Order objects after the order is filled, so we can null it here
   if (entryOrder != null && entryOrder == order)
   {
       if (order.OrderState == OrderState.Cancelled && order.Filled == 0)
           entryOrder = null;
       if (order.OrderState == OrderState.Filled)
           entryOrder = null;
   }

```

### Terminating custom resources

Use a flag to track when resources have been set up properly before attempting to destroy them.

| Why |
| --- |
| Checking that an object has been configured ensures that values not destroyed prematurely. You can read more about this subject on [Understanding the life cycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of). |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.Configure)
   {
       myObject = new object();
       // set a flag to indicator object has been configured
       configured = true;
   }

   else if (State == State.Terminated)
   {
       // only dispose of object if it has been configured
       if (configured)
       {
           myObject.Dispose();
       }
   }
}

```

## [Error handling practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#error-handling-practices)

### Safely accessing reference objects

Although there are documented States where objects are available, the implementation could change. If you are accessing a reference object, please do so by first checking that the object is not null.

```jsx-150469391 csharp
// Best practice

// checking to ensure chart control is available in all situations
// will help to ensure this logic below does not generate errors at a later time
if(ChartControl != null)
{
   myBackgroundBrush = ChartControl.Properties.ChartBackground;
}

```

### Accessing objects which terminate

To protect against race conditions and access errors, you should temporarily check for reference errors any time you attempt to do something with an object.

| Why |
| --- |
| **OnStateChange()** runs asynchronous to other **NinjaScript** events. You can run into scenarios where you **State.Terminated** logic is called in the middle of **OnBarUpdate()**, **OnRender()** etc. |

```jsx-150469391 csharp
// Best practice

protected override void OnStateChange()
{
   // this logic runs asynchronously to other events
   if (State == State.Terminated)
   {
       myObject = null;
   }
}
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if (myObject == null)
       return;

   // for safety, always check for null references before attempting to access an object
   // even if you have once checked for null references earlier run-time
   if (myObject != null)
       myObject.DoSomething();
}

```

### Proving instructions for non-ninjascript properties

Do not attempt to modify existing UI "Properties" to meet your specific needs. These features are exposed to allow you to read the environment state and make decisions to alter how your code executes, but should not be relied on to modify settings on behalf of the user. While these objects from these classes have setters for technical reasons, you should not attempt to amend the values through code. Instead, you should issue warnings or log errors instructing users to modify settings when required:

| Why |
| --- |
| **NinjaTrader** makes no guarantee that the requested changes will take effect, and user settings always take precedences. This includes the user defined **ChartControl.Properties**, **ChartBars.Properties**, and **ChartPanel.Properties**. Furthermore, two different user scripts could be installed which also attempt to modify properties you are relying which could introduce conflicts. |

```jsx-150469391 csharp
// Best practice
if (State == State.Historical)
{
   if (ChartControl.Properties.EquidistantBarSpacing == true)
   {
       Draw.TextFixed(this, "error", "This indicator works best with Equidistant BarSpacing set to false.", TextPosition.BottomRight);
   }
}

```

### Modifying UI elements and multi-threading

When interacting with UI objects, such as obtaining UI information, or modifying the existing layout, always use the **NinjaScript**'s **Dispatcher** asynchronously.

## Warning

* * *

- Improper thread handling from a **NinjaScript** object is a common cause of application deadlocks. Please be sure to read more information on [Multi-Threading Consideration for NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript).

```jsx-150469391 csharp
// Best practice
// using a Dispatcher will ensure that the corresponding action executes on the associated thread
this.Dispatcher.InvokeAsync(() =>
{
   UserControlCollection.Add(new System.Windows.Controls.TextBlock
   {
       Text = "\nAdded by the ChartControl Dispatcher."
   });
});

```

### Properly implementing try/catch blocks

Unless you are specifically debugging a method, the use of a try-catch block should be scoped to a particular area of logic. Do NOT try to handle all of your execution logic under one giant try-catch block.

| Why |
| --- |
| Larger try-catch blocks can not only be harder to debug, but can introduce performance issues at run-time. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   try
   {
       // encapsulates entire OnBarUpdate logic
   }
   catch (Exception ex)
   {
       // attempt to handle all errors in one catch
   }
}

```

### Using WPF brushes

Try to use a static predefined **Brush** if possible. If you need to customize a new brush object, make sure to **.Freeze()** the brush before using it.

| Why |
| --- |
| The pre-defined brushes are thread safe and do not require any special handling. Custom defined brushes, on the other hand, are NOT thread-safe and must be frozen otherwise cross-thread exceptions can occur. |

```jsx-150469391 csharp
// Best practice
// predefined brush
BackBrush = Brushes.Blue;

// if you are using a custom brush to e.g., modify the opacity
SolidColorBrush opaqueBlue = new SolidColorBrush(Colors.Blue) {Opacity = .25f};

// or just using at custom color not available in pre-defined brushes class
SolidColorBrush coolGreen = new SolidColorBrush(Color.FromRgb(30, 255, 128));

// you must freeze these brushes after they are constructed!
opaqueBlue.Freeze();
coolGreen.Freeze();

```

### barsAgo indexer vs. absolute bar Index

As you probably know, you can quickly look up the bar value on the chart by calling a PriceSeries< `t` \> barsAgo indexer, e.g., Close\[0\].

However, the internal indexer and pointers about the barsAgo value are only guaranteed to be correctly synced and updated during a market data event. As a result, you should favor using the absolute GetValueAt() methods during events which are not driven by price.

| Why |
| --- |
| Attempting to call the barsAgo indexer in an event method that is not driven by market data can yield unexpected results. |

```jsx-150469391 csharp
// Best practice
// OnRender is not a market data event; barsAgo pointers are not guaranteed to be in sync
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   Print(mySMA.GetValueAt(CurrentBar));
}

// same is true for you custom events
private void myCustomClickHandler(object sender, MouseButtonEventArgs e)
{
   Print(Close.GetValueAt(CurrentBar));
}

```

| Tip |
| --- |
| If you have programming requirements which rely on a **PriceSeries** indexer, you can use the **TriggerCustomEvent()** delegate which will update the internal pointers and indexes before executing the logic you specify. |

### Casting safely

Avoid type casting and type conversion as much as possible. Casting from a mixed collection of types is also prone to exceptions especially in situations that may not occur when you originally test your code.

| Why |
| --- |
| The practice to avoid code below could work in some scenarios but would generate errors if other types were added to that collection that you were not anticipating. |

```jsx-150469391 csharp
// Practice to avoid
// This would run without errors if there were ONLY type HorizontalLine on the chart
// But you risk a likely 'System.InvalidCastException' when other draw types are in that collection
foreach (HorizontalLine hLine in DrawObjects)
{
}

```

If you must cast, do so safely and avoid implicit casts to types which may not be guaranteed to succeeded.

```jsx-150469391 csharp
// Best practice
// Use the base IDrawingTool type and then cast to the desired type within the for loop
foreach (IDrawingTool hLine in DrawObjects)
{
   // Note: to prevent further errors, your type casting should be done using the "as" keyword
   // Opposed to a direct cast:
   // HorizontalLine myLine = (HorizontalLine) hLine;

   HorizontalLine myLine = hLine as HorizontalLine;

   // This will allow you to ensure the cast actually occurred
   if (myLine != null)
   {
       Print(myLine.StartAnchor.Price);
   }

```

## [Performance practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#performance-practices)

### Referencing indicator methods

In general, when calling an Indicator return method, there is some internal caching which occurs by design to help reduce memory consumption.

| Why |
| --- |
| While the designed indicator caching improves general memory performance, there is an implied cost of actually looking up the cached indicator. |

```jsx-150469391 csharp
// Practice to avoid
// each time you call the SMA() return method there is a small performance cost
// implied from the time it takes to look up the cached instance
if (Close[0] > SMA(20)[0])
{
   Print(SMA(20)[0]);
   EnterLongLimit(SMA(20)[0]);
   Draw.Dot(this, Time[0].ToString(), false, 0, SMA(20)[0], Brushes.DarkGreen);

```

## Warning

Indicator caching ONLY occurs when an indicator is recalled with the same EXACT parameters and input from the SAME calling script. (i.e. when a previously called indicator is called a second time with new parameters in the same script, a second instance will be created / cached).

If you are reusing an indicator several times through your code (especially indicators with many parameters), you can take further steps to refine performance by storing a reference to the indicator instance yourself (although it is by no means a requirement, and this suggestion does not need to be followed strictly).

```jsx-150469391 csharp
// Best practice

private SMA mySma;

protected override void OnStateChange()
{
   // when the indicator begins processing
   // save an instance of the SMA indicator with the desired input
   if (State == State.Historical)
   {
       mySma = SMA(20);
   }
}

protected override void OnBarUpdate()
{
   // use the referenced mySMA throughout the lifetime of the script
   if (Close[0] > mySma[0])
   {
       Print(mySma[0]);
       EnterLongLimit(mySma[0]);
       Draw.Dot(this, Time[0].ToString(), false, 0, mySma[0], Brushes.DarkGreen);
   }

```

### Marking object references for garbage collection

While it is not always necessary to set objects to null, doing so will mark them for garbage collection sooner and help prevent unnecessary memory resources from being utilized.

| Why |
| --- |
| In general you should be diligent to set stored memory objects to null when you are done using them, especially in situations where a **NinjaScript** object may be running for an extended period. |

```jsx-150469391 csharp
// Best practice
protected override void OnBarUpdate()
{
   // saving "myDot" creates an additional reference in memory
   Dot myDot = Draw.Dot(this, "myDot" + CurrentBar, false, Time[0], Close[0], Brushes.Blue);

   if (conditionToRemove)
   {
       // remove draw object will remove the object from the chart
       RemoveDrawObject("myDot");

       // but your local object "myDot" is still stored in memory.
       // Explicitly setting to null will ensure object is marked for garbage collection
       myDot = null;
   }
}

```

## Note

The example above demonstrates using a draw object, but the practice can be extended to any object you store in memory (e.g., orders, brushes, custom objects, etc).

### Disposing of custom resources

Dispose of objects that inherit from **IDisposable** or put into a Using statement.

| Why |
| --- |
| **NinjaTrader** is not guaranteed to dispose of objects for you. To avoid unnecessary memory consumption, always manage your resources by creating a variable and dispose of the object. |

```jsx-150469391 csharp
// Best practice
// example of object instantiated which need to be disposed
StreamWriter writer = new StreamWriter("some_file.txt");

// use the object
writer.WriteLine("Some text");

// implements IDisposbile, make sure to call .Dispose() when finished
writer.Dispose();

// or put in "using" statement which implicitly calls .Dispose() when finished
using (StreamWriter writer2 = new StreamWriter("some_file.txt"))
{
   writer2.WriteLine("Some text");
}

```

## Note

Tip: This is most commonly applicable when using **SharpDX** resources for custom rendering. Please be sure to review the information on [Best Practices for SharpDX Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

### Avoiding duplicate calculations

Be mindful where and when your potentially complex calculations would be recalculated and thus run the risk of being calculated redundantly. For example, you may have logic which only needs to calculate, e.g., once per instance, once per session, once per bar, etc.

```jsx-150469391 csharp
// Best practice

// get GetPreviousTradingDayEnd() is expensive to look up
// but value only needs to be looked up once a day -> only calculate on first bar of session
if (Bar.IsFirstBarOfSession)
{
   TradingHours.GetPreviousTradingDayEnd(Time[0]);
}

```

The same considerations would apply to variables or function calls that would not change their output value for the currently processed bar on **Calculate.OnEachTick** or **.OnPriceChange**, thus there would be no need handling them outside of **IsFirstTickOfBar**.

```jsx-150469391 csharp
// Best practice
// dedicated logic to cache the prior sum on each tick of bar
// While it is a good practice, this can cause problems for bar types which may remove last bar (see below)
if (IsFirstTickOfBar)
   priorSum = sum;

sum = priorSum + Input[0] - (CurrentBar >= Period ? Input[Period] : 0);
Value[0] = sum / (CurrentBar < Period ? CurrentBar + 1 : Period);

```

### Caching values on bars which remove last bar

Building on the previous example, be careful when caching values on the first tick of bar if using bars types which are **IsRemoveLastBarSupported**. To see how to handle these situations best, take a look at the default **SMA** indicator which has an additional logic branch which disables caching on those bar types:

```jsx-150469391 csharp
// Best practice
 // logic below disables first tick of bar caching only on bar types which remove last bar
if (BarsArray[0].BarsType.IsRemoveLastBarSupported)
{
   if (CurrentBar == 0)
       Value[0] = Input[0];
   else
   {
       double last = Value[1] * Math.Min(CurrentBar, Period);

       if (CurrentBar >= Period)
           Value[0] = (last + Input[0] - Input[Period]) / Math.Min(CurrentBar, Period);
       else
           Value[0] = ((last + Input[0]) / (Math.Min(CurrentBar, Period) + 1));
   }

```

### Precomputing values instead of calculating in **OnRender()**

To preserve good performance, always err on the side of caution if you are using **OnRender** for any calculation logic.

| Why |
| --- |
| **OnRender()** is called frequently as you interact with the Chart, which can cause calculations to occur much more often than the related market data events and can cause unnecessary spikes in CPU consumption. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // continually recalling the same value methods is unnecessary in this situation
   double myValue = Bars.GetClose(CurrentBar) + Bars.GetOpen(CurrentBar);

   // render myValue
}

```

```jsx-150469391 csharp
// Best practice
private double myValue;

protected override void OnBarUpdate()
{
   // myValue only needs to update when OnBarUpdate() is called
   // and then can be passed to OnRender() for chart rendering purposes
   myValue = Close[0] + Open[0];
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // if needed, you can always check that myValue has actually been set
   if (myValue > double.MinValue)
   {
       // render myValue
   }
}

```

### Restricting **OnRender()** calculations to visible **ChartBars**

Use the **ChartBars.FromIndex** and **ChartBars.ToIndex** to limit calculations to only what is visible on the chart.

| Why |
| --- |
| Rendering should be reserved for rendering on what is visible on the Chart. Performing calculations on bar index which are not visible can cause random spikes in CPU consumption. |

```jsx-150469391 csharp
// Best practice
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // restricting this loop to only the ChartBars.From/ToIndex limits the loop to only what is visible on the chart
   for (int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
   {
       Print(ChartControl.GetSlotIndexByX(barIndex));
   }
}

```

### Using **DrawObjects** vs custom graphics in **OnRender()**

When using **Draw methods**, a new instance of the **Draw** object is created including its custom rendering and calculation logic. These methods are convenient in many situations, but can quickly introduce performance issues if used too liberally. In some situations, you may see better performance for rendering via **SharpDX** in **OnRender()**.

| Why |
| --- |
| Each draw object instance will see its own **OnRender()** called to render values. If you instead implement custom rendering in the your object, you would only see a single **OnRender()** call for your custom created graphics. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   // this would draw a dot on every bar on the chart
   // each instance would need to call its own OnRender() method
   // not a very efficient use a draw method
   Draw.Dot(this, "everyDot" + CurrentBar, false, 0, Close[0], Brushes.Blue);
}

```

With just a little extra code (much less than what is in the **Draw methods**) custom **SharpDX** rendering greatly reduces CPU and Memory consumption. Please ensure a **Direct2D1** factory would only be instantiated from **OnRender()** or **OnRenderTargetChanged()** (which run in the UI thread), as access from other threads outside those methods could cause a degradation in performance.

```jsx-150469391 csharp
// Best practice
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // achieves the same effect of drawing a dot on every bar
   // but only needs to call your object's OnRender()
   for (int index = ChartBars.FromIndex; index <= ChartBars.ToIndex; index++)
   {
       float price = chartScale.GetYByValue(Close.GetValueAt(index));
       float bar = chartControl.GetXByBarIndex(ChartBars, index);
       float radius = (float) chartControl.BarWidth;

       SharpDX.Direct2D1.Ellipse dot = new SharpDX.Direct2D1.Ellipse(new SharpDX.Vector2(bar, price), radius, radius);

       using (SharpDX.Direct2D1.SolidColorBrush brush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue))
       {
           RenderTarget.FillEllipse(dot, brush);
       }
   }
}

```

## Note

One of the advantages of using a **Draw.Method** is the returned **Draw** Objects contains metadata which could be used later (such as for obtain the bar index or price value of the dot later on). If you would use this metadata later on, using a **Draw method** would be in your best interests. However, if you are solely looking to render figures on a chart, favoring your custom **SharpDX** methods can drastically improve performance.

### Responding to user events

Do NOT use **OnRender()** for purposes other than rendering. If you need events to hook into user interactions, consider adding your own event handler. The example below shows registering the **ChartPanel** **MouseDown** event and registering a custom WPF control.

| Why |
| --- |
| **OnRender()** may call more or less frequently than you anticipated. Using your own custom event handlers allows you control and isolate user event logic you are looking to capture. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.Historical)
   {
       // subscribe to chart panel mouse down event
       if (ChartPanel != null) ChartPanel.MouseDown += DoUserClickedChartPanelEvent;

       // subscribe to a custom UI element mouse down event
       if (myWPFControl != null) myWPFControl.MouseDown += DoCustomWPFControlClickEvent;
   }

   else if (State == State.Terminated)
   {
       // remember to unsubscribe when finished
       if (ChartPanel != null) ChartPanel.MouseDown -= DoUserClickedChartPanelEvent;
       if (myWPFControl != null) myWPFControl.MouseDown -= DoCustomWPFControlClickEvent;
   }
}

private void DoUserClickedChartPanelEvent(object sender, MouseButtonEventArgs e)
{
   Print("User clicked on the ChartPanel, executing custom mouse down logic...");
}

private void DoCustomWPFControlClickEvent(object sender, MouseButtonEventArgs e)
{
   Print("User clicked on my button, executing button logic...");
}

```

### Delaying logic for a particular time interval

Do NOT call **Thread.Sleep()** as it will lock the Instrument thread executing your **NinjaScript** object.

| Why |
| --- |
| Market data events exposed to **NinjaScript** run on the underlying Instrument thread pool shared by all Instruments. Sleeping the underlying thread of your object will cause the entire Instrument thread to sleep, adversely affecting other features using that same Instrument. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar && State == State.Realtime)
   {
       Print("Run some logic before:: " + DateTime.Now);
       Thread.Sleep(5000); // sleeping the Instrument thread will have adverse effects on elements outside of your script!
       Print("Run some logic after: " + DateTime.Now);
   }
}

```

Instead, try using a **Timer** object if you need to delay logic execution.

```jsx-150469391 csharp
// Best practice
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar && State == State.Realtime)
   {
       // Instead of Thread.Sleep for, create a timer that runs at the desired interval
       System.Windows.Forms.Timer timer = new System.Windows.Forms.Timer {Interval = 5000};

       // queue the "after" logic to run when the timer elapses
       timer.Tick += delegate
       {
           timer.Stop(); // make sure to stop the timer to only fire ones (if desired)
           Print("Run some logic after: " + DateTime.Now);
           timer.Dispose(); // make sure to dispose of the timer
       };

       Print("Run some logic before: " + DateTime.Now);

       timer.Start(); // start the timer immediately following the "before" logic
   }

```

## [Miscellaneous practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#miscellaneous-practices)

### Floating-point comparison

Be aware of floating-point precision problems. It can sometimes be more reliable to check within a certain degree of tolerance, such as the **TickSize**.

| Why |
| --- |
| You can read more about [Floating-Point Arithmetic](http://ninjatrader.com/support/forum/showthread.php?t=3929) as it applies to **NinjaTrader** on our support forum. |

```jsx-150469391 csharp
// Practice to avoid

// depending on how Value[0] was calculated, it could be off by a degree of floating points
// where this logic below would never be true
// e.g., 2050.2499999 vs 2050.50
if (Value[0] == Close[0])
{
   // do something
}

```

```jsx-150469391 csharp
// Best practice

// you can avoid these precision issues by rewriting the comparison to evaluate within a certain tolerance.
if (Math.Abs(Value[0] - Close[0]) < TickSize)
{
   // do something
}

// You will also see NinjaTrader developed objects use a custom Extension Method
// double.ApproxCompare() which Returns an int based on a Epsilon value:
if (Close[0].ApproxCompare(Value[0]) == 0)
{
   // do something
}

```

### Creating user defined parameter types / enums

When creating enums for your **NinjaScript** objects, it is strongly suggested to define those outside the class and in a custom namespace. A reference sample providing all details could be [found here](https://developer.ninjatrader.com/docs/desktop/creating_a_user_defined_parameter_type_enum).

### Efficiently debugging

Extremely liberal use of **Log()** and **Print()** methods can represent a performance hit on your PC as it takes memory and time to process each one of those method calls. When running custom **NinjaScript**, especially when using **Calculate = Calculate.OnEachTick**, please be mindful of how often **Log()** and **Print()** methods are processed as it can quickly consume PC resources.

- **Log()** method should not be used except for critical messages as each log entry makes it to the Control Center log which stays active till the end of the day. Excessive logging can result in huge amounts of memory being allocated just to display all the log messages which would mean less memory for **NinjaTrader** to do other tasks.
- **Print()** method can be used more liberally than the **Log()** method, but can still represent a performance hit if used with extremely high frequency. Consider decreasing the printing from your script if you experience slowdowns when running the script.

### Debug Mode

The debug mode should only be used if you are actively debugging a script and [attached to a debugger](https://developer.ninjatrader.com/docs/desktop/visual_studio_debugging).

| Why |
| --- |
| Debug Mode will compile all of the files in the custom project as a "Debug" build, which omits certain optimizations which occur in the C# compilation process. It is more efficient to use your custom objects in the default "Release" build if you are using your scripts during production. |

To disable Debug Mode:

- Right mouse click in any **NinjaScript Editor**
- Ensure the "Debug Mode" menu item is unchecked
- Press F5 to recompile your scripts
- Your scripts will be re-built using "Release" mode

### Known **NinjaScript** Wrappers limitations

- The **NinjaScript** editor detects code changes in external editors, and will compile on code changes, however code will only be automatically generated by the **NinjaScript** editor if it's edited within the **NinjaScript** editor itself (or **Visual Studio**).
- Wrappers cannot be generated automatically for partial and abstract classes.
- Code in the Properties region of the **NinjaScript** object cannot be commented out with the /\*\*/ style commenting, as it will cause issues with the wrapper generation. Code must be commented out with the // style.
- Subclassing would not allow for wrappers to be generated.

There are some best practices to be aware of when developing **NinjaScript** classes. The following tables present a non-exhaustive list of considerations to keep in mind when designing and implementing your code.

## Note

- NinjaTrader is multi-threaded and event driven. Always assume that any of the methods you implement in NinjaScript could be called from another thread.

## [State management practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#state-management-practices)

### Managing Resources

- The **OnStateChange()** method is called anytime there has been a change of **State** and can be used to help you setup, manage, and destroy several types of resources. Where these values are setup is highly dependent on the kind of resource you are using. The section below will cover how to manage various resources throughout different states.

### Setting Default UI Property Grid values

- Reserve **State.SetDefaults** for defaulting any public properties you wish to have exposed on the UI property grid. You should also use this **State** for setting default desired **NinjaScript** property behavior which can be overridden from the property grid (e.g. **Calculate**, **IsOverlay**, etc.). For Plots and Lines you wish to configure, **AddPlot()**, **AddLine()** should also have their default values set during this **State**.

| Why |
| --- |
| Public values of the **NinjaScript** object in **SetDefaults** are pushed to the UI property grid for an opportunity to change settings of your object. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // these are the values that show up as default on the UI
   if (State == State.SetDefaults)
   {
     Calculate = Calculate.OnPriceChange;
     IsOverlay = false;

     Period = 50;

     AddPlot(Brushes.Blue, "Plot Value");
     AddLine(Brushes.Gray, 100, "Threshold");
   }

```

For public properties you do NOT wish exposed to the UI property grid, set the **Browsable** attribute to false:

```jsx-150469391 csharp
// Best practice
[Browsable(false)] // prevents from showing up on the UI property grid
public int Communicator { get; set;

```

On indicators, properties you wish to set from other objects, set the **NinjaScriptPropertyAttribute**:

```jsx-150469391 csharp
// Best practice
[NinjaScriptProperty] // can now call **MyIndicator**(20) from another object
public int Period { get; set; }

```

The default behavior is to serialize any public properties and fields to a Workspace or Template file when saving. However, not all objects can be serialized - or you may wish to exclude a property from being saved and restored. For these scenarios, set the **XmlIgnore** attribute to the property:

```jsx-150469391 csharp
// Best practice
[XmlIgnore] // removes from serialization
public Brush DownBrush
{ get; set; }

```

As a best practice as well, your **NinjaScript** should not have any public fields, since those would get serialized as well - which means their state would be persisted, which in turn could lead to unexpected outcomes.

## Note

- See the [Working with Brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes) section of the Help Guide for information on properly serializing brushes.

### Calculating run-time object values

Do not attempt to do advanced calculations or try to access object references in **State.SetDefaults**. This **State** should be kept as lean as possible, and any calculation logic should be delayed until at least **State.Configure**.

| Why |
| --- |
| Your object will be called in situations you may not be expecting. You can read more about this subject on [Understanding the life cycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of). |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       // logic could take longer than desired as the list of indicator names is populated
       for (int i = 0; i <= array.length; i++)
           DoWork(i);

       // possible null reference exception since **TickSize** is not set yet
       Period = 5 * TickSize;
   }

```

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // Complex operations should be delayed to >= State.Configure
   if (State == State.Configure)
   {
       for (int i = 0; i <= array.length; i++)
           DoWork(i);
   }

   // information related to market data is not available until at least State.DataLoaded
   else if (State == State.DataLoaded)
   {
       Period = 5 * TickSize;
   }
}

```

### Setting class level variables

Do not set variables at the class level unless they are constant. You should delay setting or resetting variables until the **State** has reached **State.Configure**. You can use **const** keyword to differentiate values which do not change from variables which do change.

| Why |
| --- |
| Waiting to set up and define resources until the object has been configured ensures that values not set up and declared prematurely. |

```jsx-150469391 csharp
// Best practice
// value is always 5, it can be made constant and declared at the class level
private const int multiplier = 5;

// these values can change, may be better to delay setting until State.Configure
private int counter;
private List<int> myList;

protected override void OnStateChange()
{
   if (State == State.Configure)
   {
       counter = 0;
       myList = new List<int>();
   }

```

### Resetting class level variables for Strategy Analyzer Optimization

To take advantage of performance optimizations, developers may need to reset class level variables in the strategy otherwise unexpected results can occur.

| Why |
| --- |
| When optimizing a strategy, instances may or may not be recycled depending on the strategy **IsInstantiatedOnEachOptimizationIteration** setting. |

```jsx-150469391 csharp
// Best practice
// examples of fields which need to be reset
private double myDouble;
private bool myBool;
private DateTime myDateTime;
private Order myOrderObject;
private Brush myBrushObject;
private Array myIntArray;
private List<object> myList;
private SMA mySMAIndicator;
private Series<double> mySeries;

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       // disabled to take advantage of performance gains
       // However any strategy state that would be mutable after State.SetDefaults needed to be reset for the next run.
       IsInstantiatedOnEachOptimizationIteration = false;
   }
   else if (State == State.Configure)
   {
       // Since these values are not dependent on bars, they can be reset as early as State.Configure
       myDouble = double.MinValue;
       myBool = false;
       myDateTime = DateTime.MinValue;
       myOrderObject = null;
       myBrushObject = null;

       if (myIntArray != null)
           Array.Clear(myIntArray, 0, myIntArray.Length);
       else
           myIntArray = new int[20];

       if (myList != null)
           myList.Clear();
       else
           myList = new List<object>();
   }

   else if (State == State.DataLoaded)
   {
       // Since these values do are dependent on bars, they should only reset during State.DataLoaded
       mySMAIndicator = SMA(14);
       mySeries = new Series<double>(this);
   }

```

### Accessing properties related to market data

Do not attempt to access objects related to instrument market data until the **State** has reached **State.DataLoaded**.

| Why |
| --- |
| Waiting to access objects that depend on market data until **DataLoaded** prevents access errors in all scenarios. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       // these objects and their related members are not available until State.DataLoaded
       Print(Bars.Count);
       Print(Instrument.FullName);
       Print(BarsPeriod.BarsPeriodType);
       Print(TradingHours.TimeZon;
       Print(Input);
   }
}

```

## Note

- All additional data series must be added in **State.Configure** (this includes series that any hosted script potentially needs as well - [more info](https://developer.ninjatrader.com/docs/desktop/adddataseries)). Since objects such as **Instrument**, **BarsPeriod**, **TradingHours**, etc. are NOT guaranteed to be available until **State.DataLoaded**, you cannot reliably use the primary instrument properties as arguments in **AddDataSeries()**. Attempting to add a data series dynamically is NOT guaranteed and therefore should be avoided. In some cases, you may be able to use a **BarsRequest()** to obtain market data for other instruments and intervals.

### Setting up resources that rely on market data

For objects which depend on market data, delay their construction until the **State** has reached **State.DataLoaded**.

| Why |
| --- |
| Waiting to construct objects that depend on market data until **DataLoaded** ensures that their underlying input contains significant values in all scenarios. |

```jsx-150469391 csharp
// Best practice
// these resources depend on bars, wait until State.DataLoaded to instantiated
private EMA myEMA;
private Series<double> mySeries;
private SessionIterator mySessionIterator;

protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       myEMA = EMA(20);
       mySeries = new Series<double>(this);
       mySessionIterator = new SessionIterator(Bars);
   }

```

### Accessing element on the UI

For objects which exist on the UI (e.g., **ChartControl**, **ChartPanel**, **ChartBars**, **NTWindow**, etc.) wait until the **State** has reached **State.Historical**. This practice is correct for both reading properties or should you wish to add custom elements to the existing UI.

| Why |
| --- |
| **NinjaTrader** UI related objects are not guaranteed to be available until historical data processing has started. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   // wait until at least State.Historical
   if (State == State.Historical)
   {
       // and double check UI object is not null before accessing
       if (ChartControl != null)
       {
           Print(ChartControl.Properties.ChartBackground);
       }
   }
}

```

### Transitioning order references from historical to real-time

When dealing with strategy based orders which have transitioned from historical to real-time, you will need to ensure that locally stored order references are also updated.

| Why |
| --- |
| As the core order object updates, **NinjaTrader** has no specific way to update your locally stored order references. You can read more about this subject on the Advanced Order Handling topic: [Transitioning order references from historical to live](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling). |

```jsx-150469391 csharp
// Best practice
private Order entryOrder = null;

protected override void OnBarUpdate()
{
   if (entryOrder == null && Close[0] > Open[0])
       entryOrder = EnterLongLimit("myEntryOrder", Low[0]);
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
   // One time only, as we transition from historical
   // Convert any old historical order object references to the live order submitted to the real-time account
   if (entryOrder != null && entryOrder.IsBacktestOrder && State == State.Realtime)
       entryOrder = GetRealtimeOrder(entryOrder);

   // Null entryOrder if filled or cancelled. We do not use the Order objects after the order is filled, so we can null it here
   if (entryOrder != null && entryOrder == order)
   {
       if (order.OrderState == OrderState.Cancelled && order.Filled == 0)
           entryOrder = null;
       if (order.OrderState == OrderState.Filled)
           entryOrder = null;
   }

```

### Terminating custom resources

Use a flag to track when resources have been set up properly before attempting to destroy them.

| Why |
| --- |
| Checking that an object has been configured ensures that values not destroyed prematurely. You can read more about this subject on [Understanding the life cycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of). |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.Configure)
   {
       myObject = new object();
       // set a flag to indicator object has been configured
       configured = true;
   }

   else if (State == State.Terminated)
   {
       // only dispose of object if it has been configured
       if (configured)
       {
           myObject.Dispose();
       }
   }
}

```

## [Error handling practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#error-handling-practices)

### Safely accessing reference objects

Although there are documented States where objects are available, the implementation could change. If you are accessing a reference object, please do so by first checking that the object is not null.

```jsx-150469391 csharp
// Best practice

// checking to ensure chart control is available in all situations
// will help to ensure this logic below does not generate errors at a later time
if(ChartControl != null)
{
   myBackgroundBrush = ChartControl.Properties.ChartBackground;
}

```

### Accessing objects which terminate

To protect against race conditions and access errors, you should temporarily check for reference errors any time you attempt to do something with an object.

| Why |
| --- |
| **OnStateChange()** runs asynchronous to other **NinjaScript** events. You can run into scenarios where you **State.Terminated** logic is called in the middle of **OnBarUpdate()**, **OnRender()** etc. |

```jsx-150469391 csharp
// Best practice

protected override void OnStateChange()
{
   // this logic runs asynchronously to other events
   if (State == State.Terminated)
   {
       myObject = null;
   }
}
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if (myObject == null)
       return;

   // for safety, always check for null references before attempting to access an object
   // even if you have once checked for null references earlier run-time
   if (myObject != null)
       myObject.DoSomething();
}

```

### Proving instructions for non-ninjascript properties

Do not attempt to modify existing UI "Properties" to meet your specific needs. These features are exposed to allow you to read the environment state and make decisions to alter how your code executes, but should not be relied on to modify settings on behalf of the user. While these objects from these classes have setters for technical reasons, you should not attempt to amend the values through code. Instead, you should issue warnings or log errors instructing users to modify settings when required:

| Why |
| --- |
| **NinjaTrader** makes no guarantee that the requested changes will take effect, and user settings always take precedences. This includes the user defined **ChartControl.Properties**, **ChartBars.Properties**, and **ChartPanel.Properties**. Furthermore, two different user scripts could be installed which also attempt to modify properties you are relying which could introduce conflicts. |

```jsx-150469391 csharp
// Best practice
if (State == State.Historical)
{
   if (ChartControl.Properties.EquidistantBarSpacing == true)
   {
       Draw.TextFixed(this, "error", "This indicator works best with Equidistant BarSpacing set to false.", TextPosition.BottomRight);
   }
}

```

### Modifying UI elements and multi-threading

When interacting with UI objects, such as obtaining UI information, or modifying the existing layout, always use the **NinjaScript**'s **Dispatcher** asynchronously.

## Warning

* * *

- Improper thread handling from a **NinjaScript** object is a common cause of application deadlocks. Please be sure to read more information on [Multi-Threading Consideration for NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript).

```jsx-150469391 csharp
// Best practice
// using a Dispatcher will ensure that the corresponding action executes on the associated thread
this.Dispatcher.InvokeAsync(() =>
{
   UserControlCollection.Add(new System.Windows.Controls.TextBlock
   {
       Text = "\nAdded by the ChartControl Dispatcher."
   });
});

```

### Properly implementing try/catch blocks

Unless you are specifically debugging a method, the use of a try-catch block should be scoped to a particular area of logic. Do NOT try to handle all of your execution logic under one giant try-catch block.

| Why |
| --- |
| Larger try-catch blocks can not only be harder to debug, but can introduce performance issues at run-time. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   try
   {
       // encapsulates entire OnBarUpdate logic
   }
   catch (Exception ex)
   {
       // attempt to handle all errors in one catch
   }
}

```

### Using WPF brushes

Try to use a static predefined **Brush** if possible. If you need to customize a new brush object, make sure to **.Freeze()** the brush before using it.

| Why |
| --- |
| The pre-defined brushes are thread safe and do not require any special handling. Custom defined brushes, on the other hand, are NOT thread-safe and must be frozen otherwise cross-thread exceptions can occur. |

```jsx-150469391 csharp
// Best practice
// predefined brush
BackBrush = Brushes.Blue;

// if you are using a custom brush to e.g., modify the opacity
SolidColorBrush opaqueBlue = new SolidColorBrush(Colors.Blue) {Opacity = .25f};

// or just using at custom color not available in pre-defined brushes class
SolidColorBrush coolGreen = new SolidColorBrush(Color.FromRgb(30, 255, 128));

// you must freeze these brushes after they are constructed!
opaqueBlue.Freeze();
coolGreen.Freeze();

```

### barsAgo indexer vs. absolute bar Index

As you probably know, you can quickly look up the bar value on the chart by calling a PriceSeries< `t` \> barsAgo indexer, e.g., Close\[0\].

However, the internal indexer and pointers about the barsAgo value are only guaranteed to be correctly synced and updated during a market data event. As a result, you should favor using the absolute GetValueAt() methods during events which are not driven by price.

| Why |
| --- |
| Attempting to call the barsAgo indexer in an event method that is not driven by market data can yield unexpected results. |

```jsx-150469391 csharp
// Best practice
// OnRender is not a market data event; barsAgo pointers are not guaranteed to be in sync
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   Print(mySMA.GetValueAt(CurrentBar));
}

// same is true for you custom events
private void myCustomClickHandler(object sender, MouseButtonEventArgs e)
{
   Print(Close.GetValueAt(CurrentBar));
}

```

| Tip |
| --- |
| If you have programming requirements which rely on a **PriceSeries** indexer, you can use the **TriggerCustomEvent()** delegate which will update the internal pointers and indexes before executing the logic you specify. |

### Casting safely

Avoid type casting and type conversion as much as possible. Casting from a mixed collection of types is also prone to exceptions especially in situations that may not occur when you originally test your code.

| Why |
| --- |
| The practice to avoid code below could work in some scenarios but would generate errors if other types were added to that collection that you were not anticipating. |

```jsx-150469391 csharp
// Practice to avoid
// This would run without errors if there were ONLY type HorizontalLine on the chart
// But you risk a likely 'System.InvalidCastException' when other draw types are in that collection
foreach (HorizontalLine hLine in DrawObjects)
{
}

```

If you must cast, do so safely and avoid implicit casts to types which may not be guaranteed to succeeded.

```jsx-150469391 csharp
// Best practice
// Use the base IDrawingTool type and then cast to the desired type within the for loop
foreach (IDrawingTool hLine in DrawObjects)
{
   // Note: to prevent further errors, your type casting should be done using the "as" keyword
   // Opposed to a direct cast:
   // HorizontalLine myLine = (HorizontalLine) hLine;

   HorizontalLine myLine = hLine as HorizontalLine;

   // This will allow you to ensure the cast actually occurred
   if (myLine != null)
   {
       Print(myLine.StartAnchor.Price);
   }

```

## [Performance practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#performance-practices)

### Referencing indicator methods

In general, when calling an Indicator return method, there is some internal caching which occurs by design to help reduce memory consumption.

| Why |
| --- |
| While the designed indicator caching improves general memory performance, there is an implied cost of actually looking up the cached indicator. |

```jsx-150469391 csharp
// Practice to avoid
// each time you call the SMA() return method there is a small performance cost
// implied from the time it takes to look up the cached instance
if (Close[0] > SMA(20)[0])
{
   Print(SMA(20)[0]);
   EnterLongLimit(SMA(20)[0]);
   Draw.Dot(this, Time[0].ToString(), false, 0, SMA(20)[0], Brushes.DarkGreen);

```

## Warning

Indicator caching ONLY occurs when an indicator is recalled with the same EXACT parameters and input from the SAME calling script. (i.e. when a previously called indicator is called a second time with new parameters in the same script, a second instance will be created / cached).

If you are reusing an indicator several times through your code (especially indicators with many parameters), you can take further steps to refine performance by storing a reference to the indicator instance yourself (although it is by no means a requirement, and this suggestion does not need to be followed strictly).

```jsx-150469391 csharp
// Best practice

private SMA mySma;

protected override void OnStateChange()
{
   // when the indicator begins processing
   // save an instance of the SMA indicator with the desired input
   if (State == State.Historical)
   {
       mySma = SMA(20);
   }
}

protected override void OnBarUpdate()
{
   // use the referenced mySMA throughout the lifetime of the script
   if (Close[0] > mySma[0])
   {
       Print(mySma[0]);
       EnterLongLimit(mySma[0]);
       Draw.Dot(this, Time[0].ToString(), false, 0, mySma[0], Brushes.DarkGreen);
   }

```

### Marking object references for garbage collection

While it is not always necessary to set objects to null, doing so will mark them for garbage collection sooner and help prevent unnecessary memory resources from being utilized.

| Why |
| --- |
| In general you should be diligent to set stored memory objects to null when you are done using them, especially in situations where a **NinjaScript** object may be running for an extended period. |

```jsx-150469391 csharp
// Best practice
protected override void OnBarUpdate()
{
   // saving "myDot" creates an additional reference in memory
   Dot myDot = Draw.Dot(this, "myDot" + CurrentBar, false, Time[0], Close[0], Brushes.Blue);

   if (conditionToRemove)
   {
       // remove draw object will remove the object from the chart
       RemoveDrawObject("myDot");

       // but your local object "myDot" is still stored in memory.
       // Explicitly setting to null will ensure object is marked for garbage collection
       myDot = null;
   }
}

```

## Note

The example above demonstrates using a draw object, but the practice can be extended to any object you store in memory (e.g., orders, brushes, custom objects, etc).

### Disposing of custom resources

Dispose of objects that inherit from **IDisposable** or put into a Using statement.

| Why |
| --- |
| **NinjaTrader** is not guaranteed to dispose of objects for you. To avoid unnecessary memory consumption, always manage your resources by creating a variable and dispose of the object. |

```jsx-150469391 csharp
// Best practice
// example of object instantiated which need to be disposed
StreamWriter writer = new StreamWriter("some_file.txt");

// use the object
writer.WriteLine("Some text");

// implements IDisposbile, make sure to call .Dispose() when finished
writer.Dispose();

// or put in "using" statement which implicitly calls .Dispose() when finished
using (StreamWriter writer2 = new StreamWriter("some_file.txt"))
{
   writer2.WriteLine("Some text");
}

```

## Note

Tip: This is most commonly applicable when using **SharpDX** resources for custom rendering. Please be sure to review the information on [Best Practices for SharpDX Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

### Avoiding duplicate calculations

Be mindful where and when your potentially complex calculations would be recalculated and thus run the risk of being calculated redundantly. For example, you may have logic which only needs to calculate, e.g., once per instance, once per session, once per bar, etc.

```jsx-150469391 csharp
// Best practice

// get GetPreviousTradingDayEnd() is expensive to look up
// but value only needs to be looked up once a day -> only calculate on first bar of session
if (Bar.IsFirstBarOfSession)
{
   TradingHours.GetPreviousTradingDayEnd(Time[0]);
}

```

The same considerations would apply to variables or function calls that would not change their output value for the currently processed bar on **Calculate.OnEachTick** or **.OnPriceChange**, thus there would be no need handling them outside of **IsFirstTickOfBar**.

```jsx-150469391 csharp
// Best practice
// dedicated logic to cache the prior sum on each tick of bar
// While it is a good practice, this can cause problems for bar types which may remove last bar (see below)
if (IsFirstTickOfBar)
   priorSum = sum;

sum = priorSum + Input[0] - (CurrentBar >= Period ? Input[Period] : 0);
Value[0] = sum / (CurrentBar < Period ? CurrentBar + 1 : Period);

```

### Caching values on bars which remove last bar

Building on the previous example, be careful when caching values on the first tick of bar if using bars types which are **IsRemoveLastBarSupported**. To see how to handle these situations best, take a look at the default **SMA** indicator which has an additional logic branch which disables caching on those bar types:

```jsx-150469391 csharp
// Best practice
 // logic below disables first tick of bar caching only on bar types which remove last bar
if (BarsArray[0].BarsType.IsRemoveLastBarSupported)
{
   if (CurrentBar == 0)
       Value[0] = Input[0];
   else
   {
       double last = Value[1] * Math.Min(CurrentBar, Period);

       if (CurrentBar >= Period)
           Value[0] = (last + Input[0] - Input[Period]) / Math.Min(CurrentBar, Period);
       else
           Value[0] = ((last + Input[0]) / (Math.Min(CurrentBar, Period) + 1));
   }

```

### Precomputing values instead of calculating in **OnRender()**

To preserve good performance, always err on the side of caution if you are using **OnRender** for any calculation logic.

| Why |
| --- |
| **OnRender()** is called frequently as you interact with the Chart, which can cause calculations to occur much more often than the related market data events and can cause unnecessary spikes in CPU consumption. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // continually recalling the same value methods is unnecessary in this situation
   double myValue = Bars.GetClose(CurrentBar) + Bars.GetOpen(CurrentBar);

   // render myValue
}

```

```jsx-150469391 csharp
// Best practice
private double myValue;

protected override void OnBarUpdate()
{
   // myValue only needs to update when OnBarUpdate() is called
   // and then can be passed to OnRender() for chart rendering purposes
   myValue = Close[0] + Open[0];
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // if needed, you can always check that myValue has actually been set
   if (myValue > double.MinValue)
   {
       // render myValue
   }
}

```

### Restricting **OnRender()** calculations to visible **ChartBars**

Use the **ChartBars.FromIndex** and **ChartBars.ToIndex** to limit calculations to only what is visible on the chart.

| Why |
| --- |
| Rendering should be reserved for rendering on what is visible on the Chart. Performing calculations on bar index which are not visible can cause random spikes in CPU consumption. |

```jsx-150469391 csharp
// Best practice
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // restricting this loop to only the ChartBars.From/ToIndex limits the loop to only what is visible on the chart
   for (int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
   {
       Print(ChartControl.GetSlotIndexByX(barIndex));
   }
}

```

### Using **DrawObjects** vs custom graphics in **OnRender()**

When using **Draw methods**, a new instance of the **Draw** object is created including its custom rendering and calculation logic. These methods are convenient in many situations, but can quickly introduce performance issues if used too liberally. In some situations, you may see better performance for rendering via **SharpDX** in **OnRender()**.

| Why |
| --- |
| Each draw object instance will see its own **OnRender()** called to render values. If you instead implement custom rendering in the your object, you would only see a single **OnRender()** call for your custom created graphics. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   // this would draw a dot on every bar on the chart
   // each instance would need to call its own OnRender() method
   // not a very efficient use a draw method
   Draw.Dot(this, "everyDot" + CurrentBar, false, 0, Close[0], Brushes.Blue);
}

```

With just a little extra code (much less than what is in the **Draw methods**) custom **SharpDX** rendering greatly reduces CPU and Memory consumption. Please ensure a **Direct2D1** factory would only be instantiated from **OnRender()** or **OnRenderTargetChanged()** (which run in the UI thread), as access from other threads outside those methods could cause a degradation in performance.

```jsx-150469391 csharp
// Best practice
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // achieves the same effect of drawing a dot on every bar
   // but only needs to call your object's OnRender()
   for (int index = ChartBars.FromIndex; index <= ChartBars.ToIndex; index++)
   {
       float price = chartScale.GetYByValue(Close.GetValueAt(index));
       float bar = chartControl.GetXByBarIndex(ChartBars, index);
       float radius = (float) chartControl.BarWidth;

       SharpDX.Direct2D1.Ellipse dot = new SharpDX.Direct2D1.Ellipse(new SharpDX.Vector2(bar, price), radius, radius);

       using (SharpDX.Direct2D1.SolidColorBrush brush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue))
       {
           RenderTarget.FillEllipse(dot, brush);
       }
   }
}

```

## Note

One of the advantages of using a **Draw.Method** is the returned **Draw** Objects contains metadata which could be used later (such as for obtain the bar index or price value of the dot later on). If you would use this metadata later on, using a **Draw method** would be in your best interests. However, if you are solely looking to render figures on a chart, favoring your custom **SharpDX** methods can drastically improve performance.

### Responding to user events

Do NOT use **OnRender()** for purposes other than rendering. If you need events to hook into user interactions, consider adding your own event handler. The example below shows registering the **ChartPanel** **MouseDown** event and registering a custom WPF control.

| Why |
| --- |
| **OnRender()** may call more or less frequently than you anticipated. Using your own custom event handlers allows you control and isolate user event logic you are looking to capture. |

```jsx-150469391 csharp
// Best practice
protected override void OnStateChange()
{
   if (State == State.Historical)
   {
       // subscribe to chart panel mouse down event
       if (ChartPanel != null) ChartPanel.MouseDown += DoUserClickedChartPanelEvent;

       // subscribe to a custom UI element mouse down event
       if (myWPFControl != null) myWPFControl.MouseDown += DoCustomWPFControlClickEvent;
   }

   else if (State == State.Terminated)
   {
       // remember to unsubscribe when finished
       if (ChartPanel != null) ChartPanel.MouseDown -= DoUserClickedChartPanelEvent;
       if (myWPFControl != null) myWPFControl.MouseDown -= DoCustomWPFControlClickEvent;
   }
}

private void DoUserClickedChartPanelEvent(object sender, MouseButtonEventArgs e)
{
   Print("User clicked on the ChartPanel, executing custom mouse down logic...");
}

private void DoCustomWPFControlClickEvent(object sender, MouseButtonEventArgs e)
{
   Print("User clicked on my button, executing button logic...");
}

```

### Delaying logic for a particular time interval

Do NOT call **Thread.Sleep()** as it will lock the Instrument thread executing your **NinjaScript** object.

| Why |
| --- |
| Market data events exposed to **NinjaScript** run on the underlying Instrument thread pool shared by all Instruments. Sleeping the underlying thread of your object will cause the entire Instrument thread to sleep, adversely affecting other features using that same Instrument. |

```jsx-150469391 csharp
// Practice to avoid
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar && State == State.Realtime)
   {
       Print("Run some logic before:: " + DateTime.Now);
       Thread.Sleep(5000); // sleeping the Instrument thread will have adverse effects on elements outside of your script!
       Print("Run some logic after: " + DateTime.Now);
   }
}

```

Instead, try using a **Timer** object if you need to delay logic execution.

```jsx-150469391 csharp
// Best practice
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar && State == State.Realtime)
   {
       // Instead of Thread.Sleep for, create a timer that runs at the desired interval
       System.Windows.Forms.Timer timer = new System.Windows.Forms.Timer {Interval = 5000};

       // queue the "after" logic to run when the timer elapses
       timer.Tick += delegate
       {
           timer.Stop(); // make sure to stop the timer to only fire ones (if desired)
           Print("Run some logic after: " + DateTime.Now);
           timer.Dispose(); // make sure to dispose of the timer
       };

       Print("Run some logic before: " + DateTime.Now);

       timer.Start(); // start the timer immediately following the "before" logic
   }

```

## [Miscellaneous practices](https://developer.ninjatrader.com/docs/desktop/ninjascript_best_practices\#miscellaneous-practices)

### Floating-point comparison

Be aware of floating-point precision problems. It can sometimes be more reliable to check within a certain degree of tolerance, such as the **TickSize**.

| Why |
| --- |
| You can read more about [Floating-Point Arithmetic](http://ninjatrader.com/support/forum/showthread.php?t=3929) as it applies to **NinjaTrader** on our support forum. |

```jsx-150469391 csharp
// Practice to avoid

// depending on how Value[0] was calculated, it could be off by a degree of floating points
// where this logic below would never be true
// e.g., 2050.2499999 vs 2050.50
if (Value[0] == Close[0])
{
   // do something
}

```

```jsx-150469391 csharp
// Best practice

// you can avoid these precision issues by rewriting the comparison to evaluate within a certain tolerance.
if (Math.Abs(Value[0] - Close[0]) < TickSize)
{
   // do something
}

// You will also see NinjaTrader developed objects use a custom Extension Method
// double.ApproxCompare() which Returns an int based on a Epsilon value:
if (Close[0].ApproxCompare(Value[0]) == 0)
{
   // do something
}

```

### Creating user defined parameter types / enums

When creating enums for your **NinjaScript** objects, it is strongly suggested to define those outside the class and in a custom namespace. A reference sample providing all details could be [found here](https://developer.ninjatrader.com/docs/desktop/creating_a_user_defined_parameter_type_enum).

### Efficiently debugging

Extremely liberal use of **Log()** and **Print()** methods can represent a performance hit on your PC as it takes memory and time to process each one of those method calls. When running custom **NinjaScript**, especially when using **Calculate = Calculate.OnEachTick**, please be mindful of how often **Log()** and **Print()** methods are processed as it can quickly consume PC resources.

- **Log()** method should not be used except for critical messages as each log entry makes it to the Control Center log which stays active till the end of the day. Excessive logging can result in huge amounts of memory being allocated just to display all the log messages which would mean less memory for **NinjaTrader** to do other tasks.
- **Print()** method can be used more liberally than the **Log()** method, but can still represent a performance hit if used with extremely high frequency. Consider decreasing the printing from your script if you experience slowdowns when running the script.

### Debug Mode

The debug mode should only be used if you are actively debugging a script and [attached to a debugger](https://developer.ninjatrader.com/docs/desktop/visual_studio_debugging).

| Why |
| --- |
| Debug Mode will compile all of the files in the custom project as a "Debug" build, which omits certain optimizations which occur in the C# compilation process. It is more efficient to use your custom objects in the default "Release" build if you are using your scripts during production. |

To disable Debug Mode:

- Right mouse click in any **NinjaScript Editor**
- Ensure the "Debug Mode" menu item is unchecked
- Press F5 to recompile your scripts
- Your scripts will be re-built using "Release" mode

### Known **NinjaScript** Wrappers limitations

- The **NinjaScript** editor detects code changes in external editors, and will compile on code changes, however code will only be automatically generated by the **NinjaScript** editor if it's edited within the **NinjaScript** editor itself (or **Visual Studio**).
- Wrappers cannot be generated automatically for partial and abstract classes.
- Code in the Properties region of the **NinjaScript** object cannot be commented out with the /\*\*/ style commenting, as it will cause issues with the wrapper generation. Code must be commented out with the // style.
- Subclassing would not allow for wrappers to be generated.