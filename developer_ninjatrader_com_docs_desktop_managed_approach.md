The Managed approach in **NinjaScript** is designed to offer the greatest ease of use for beginner to intermediate programmers. The order methods are wrapped in a convenience layer that allows you to focus on your system's trading rules, leaving the underlying mechanics of order management and the relationships between entry orders, exit orders, and positions to **NinjaTrader**. This approach is best suited for simple to moderate order complexity, and can be further broken down into a Basic/Common Managed approach and a more [Advanced](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) Managed approach. The following section will discuss the use of the Basic/Common approach.

A few key points to keep in mind:

- Orders are submitted as live and working when a strategy is running in real-time

- Profit target, stop loss and trail stop orders are submitted immediately when an entry order is filled, and are tied together via OCO (One Cancels Other)

- Order changes and cancellations are queued in the event that the order is in a state where it can't be cancelled or modified

- By default, orders submitted via **Entry()** and **Exit()** methods automatically cancel at the end of a bar if not re-submitted

- **Entry()** methods will reverse the position automatically. For example if you are in a 1 contract long position and now call **EnterShort()** -\> you will see 2 executions, one to close the prior long position and the other to get you into the desired 1 contract short position.

- Via the [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) , [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) , [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) and [SetParabolicStop](https://developer.ninjatrader.com/docs/desktop/setparabolicstop) methods


## [Order submission for entry and exit methods - basic operation](https://developer.ninjatrader.com/docs/desktop/managed_approach\#order-submission-for-entry-and-exit-methods---basic-operation)

## Note

- Orders are primarily submitted from within the **OnBarUpdate()** method when a specific order method is called. By default, orders are kept alive, provided they are re-submitted on each call of the **OnBarUpdate()** method. If an order is not re-submitted, it is then canceled. Orders can be modified by re-submitting them with changed parameters (a new limit price, for example). In the example below, a Buy Limit order is working at the bid price, provided that the Close price of the current bar is greater than the current value of the 20 period Simple Moving Average. If the entry condition is no longer true and the order is still active, it will be immediately canceled.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Entry condition
     if (Close[0] > SMA(20)[0])
         EnterLongLimit(GetCurrentBid());
}

```

This technique allows you the quickest and easiest order submission method suitable for programmers of all levels. Should you want to submit an order and not have to keep re-submitting it to keep it alive you can use an [advanced approach](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) reserved for experienced programmers, which includes an option to keep orders alive until specifically canceled in code.

## [Order Entry Methods](https://developer.ninjatrader.com/docs/desktop/managed_approach\#order-entry-methods)

## Note

- Order Entry Methods Order entry methods are used to submit orders of different types. Methods exist to submit Market, Market-if-Touched, Limit, Stop Market, and Stop Limit orders. See the order-entry method pages listed in the help guide table of contents under this page for more information on a specific method. Signal Names on Entry Methods You can optionally tag an entry order with a signal name. Signal names are used to identify executions resulting from the order on a chart and in performance reports. Market positions created from a tagged entry method are marked with the signal name which serves two purposes:
- Used to tie an exit method to a specific position
- Used to identify unique entries in a strategy Below is an example of placing a Market entry order and an associated Limit exit order, tied together by the signal name of the entry order.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (CurrentBar < 1) return;

   if (Close[0] > Close[1])
   {
       // Place a Market order to enter long
       EnterLong("longEntry");

       // Manually place a Profit Target 10 ticks above the current price, tied to the entry order's SignalName
       ExitLongLimit(Close[0] + (10 * TickSize), "longEntry");
   }
}

```

### Defining how Entry Methods are Processed in a Strategy

You can limit how many entry methods are processed by determining the maximum number of entries in a single direction across all entry methods, or across unique signal names. The following properties can be set in the Strategies window when adding a strategy to a chart or to the Strategies tab of the Control Center window.

- [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection) property - Sets the maximum number of entries in a single direction
- [EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling) property - Determines if EntriesPerDirection applies across all entries or for entries with specified signal names

The example code below illustrates how the above properties control the processing of entry methods. The code contains two entry conditions and two **EnterLong** methods, each tagged with unique signal names.

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       EntriesPerDirection = 1;
       EntryHandling = EntryHandling.AllEntries;
   }
}

protected override void OnBarUpdate()
{
   // Entry condition 1
   if (CrossAbove(SMA(10), SMA(20), 1))
       EnterLong("Condition 1 Entry");

   // Entry condition 2
   if (CrossAbove(RSI(14, 3), 30, 1))
       EnterLong("Condition 2 Entry");
}

```

### Entry Methods on Multi-Instrument Strategies

When running strategies that submit orders to multiple instruments, entry methods will submit orders to the instrument referenced by the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress). The following example assumes that the strategy is running on a 1 minute E-Mini S&P 500 chart. It adds an NQ data series, then enters a position on both instruments.

```jsx-150469391 csharp
protected override void OnStateChange()
{
     AddDataSeries("NQ 09-14", BarsPeriodType.Minute, 1);
}

protected override void OnBarUpdate()
{
     if (BarsInProgress == 0)
         EnterLong("ES Trade");
     else if (BarsInProgress == 1)
         EnterLong("NQ Trade");
}

```

More information on using BarsInProgress to filter instruments can be found in the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) page.

## [Quantity Type and TIF](https://developer.ninjatrader.com/docs/desktop/managed_approach\#quantity-type-and-tif)

You can set the entry order quantity and order type directly in code via the following properties:

- QuantityType - Sets the order quantity is taken from the entry method quantity property or the default strategy quantity size
- [TimeInForce](https://developer.ninjatrader.com/docs/desktop/timeinforce) property - Sets the time in force of the order

## [How to close a position](https://developer.ninjatrader.com/docs/desktop/managed_approach\#how-to-close-a-position)

- Closing a Position using a Stop Loss, Trailing Stop and/or Profit Target You can predefine a stop loss, trailing stop and/or profit target in a strategy by calling the [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss), [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) and/or [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) methods from inside the **OnStateChange()** event handler. When these methods are called, they submit live working orders in real-time as executions are reported as a result of calling an entry method. These orders are also tied via OCO (One Cancels Other). Stop losses and profit target can be generated for each fill or each position. This is determined by the "Stop & target submission" property which is set in the Strategies window. Possible values are listed below:
- ByStrategyPosition - When this is selected, only one stop loss, trail stop and/or profit target order is submitted. As entry executions come in, the order size is amended. The downside of this approach is that if you receive partial fills, the orders are re-inserted into the exchange order queue. The upside is that if you broker charges you commission per order (not per quantity), you will not incur additional commission expenses.
- PerEntryExecution - When this is selected, a stop loss, trail stop and/or profit target order is submitted for each partial fill received. The downside is that if your broker charges commission per order, you can incur very expensive commission costs if you receive partial fills. The upside is that orders are submitted as soon as possible, giving you the advantage of getting into the order queue immediately.

### Closing a Position using an Exit Method

Exit methods submit orders to close out a position in whole or in part. When closing a position with Exit orders, the order quantity will be reduced as the strategy position reduces - for example, if we use [ExitLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitlongstopmarket) and [ExitLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitlongstoplimit) to protect a position and one of those orders gets filled, the other order associated with exiting that position will reduce their quantity.

As with entry methods, more information about specific exit methods can be found in this Help Guide's table of contents, beneath this page.

### Closing a Partial Position using an Exit Method

You can close out a partial position by specifying the exit quantity. The following example first enters long for three contracts. Then, each subsequent bar update submits a market order to exit one contract until the position is completely closed. "ExitLong(1)" will be ignored if a long market position does not exist.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1))
         EnterLong(3);

     ExitLong(1);
}

```

FromEntrySignal -- Using Signal Names in Exit Methods

Identifying entries with a signal name allows you to place multiple unique entries within a single strategy and call exit methods with specified signal names, so that only a position created with the specified signal name is closed. In the example below, there are two entry conditions which create positions, and two exit conditions specifying which position to close based on the signal name.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Entry condition 1
     if (CrossAbove(SMA(10), SMA(20), 1))
         EnterLong("Condition 1 Entry");

     // Entry condition 2
     if (CrossAbove(RSI(14, 3), 30, 1))
         EnterLong("Condition 2 Entry");

     // Closes the position created by entry condition 1
     if (CrossBelow(SMA(10), SMA(20), 1))
         ExitLong("Condition 1 Entry");

     // Closes the position created by entry condition 2
     if (CrossBelow(RSI(14, 3), 70, 1))
         ExitLong("Condition 2 Entry");

```

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (Position.MarketPosition == MarketPosition.Flat)
   {
       // Entry condition 1
       if (CrossAbove(SMA(10), SMA(20), 1))
           EnterLong("Condition 1 Entry");
   }

   if (Position.MarketPosition != MarketPosition.Flat)
   {
       // Scale in condition 2 for position management
       if (CrossAbove(RSI(14, 3), 30, 1))
           EnterLong("Condition 2 Entry");

       // Exit all positions using an empty string (could also use string.Empty)
       if (CrossBelow(SMA(10), SMA(20), 1))
           ExitLong("Exit All", "");
   }
}

```

## [Understanding core order objects](https://developer.ninjatrader.com/docs/desktop/managed_approach\#understanding-core-order-objects)

- When using order methods such as [EnterLong()](https://developer.ninjatrader.com/docs/desktop/enterlong), [ExitShortLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortlimit), etc, a direct [order object](https://developer.ninjatrader.com/docs/desktop/order) is returned for the **NinjaTrader** Core. These objects can be used throughout the lifetime of your strategy to provide additional metadata concerning your strategy, as well as apply advanced concepts such as [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/cancelorder) and [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder). More information about this advanced concept which is discussed under the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Internal Order Handling Rules that Reduce Unwanted Positions](https://developer.ninjatrader.com/docs/desktop/managed_approach\#internal-order-handling-rules-that-reduce-unwanted-positions)

- To prevent situations in real-time in which you may have multiple orders working to accomplish the same task, there are some "under the hood" rules that a **NinjaScript** strategy follows when Managed order methods are called. For example, if your strategy had a limit order for 1 contract working as a Profit Target, but then your strategy was also programmed to reverse the position at the price very close to the target limit order, then submitting both orders can be risky, since it could lead to a larger position than the strategy is designed to enter if both orders got filled in quick succession by the exchange.

The following rules are true per unique signal name:

Methods that generate orders to enter a position will be ignored if:

- A position is open and an order submitted by a non market order exit method ( [ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a set method ( [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) for example) is active and the order is used to open a position in the opposite direction
- A position is open and two or more Entry methods to reverse the position are entered together. In this case the second Entry order will be ignored.
- The strategy position is flat and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- The entry signal name is not unique

Methods that generate orders to exit a position will be ignored if:

- A position is open and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a set method ( [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) for example) is active

Set() methods that generate orders to exit a position will be ignored if:

- A position is open and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a non market order exit method ( [ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit) for example) is active

The Managed approach in **NinjaScript** is designed to offer the greatest ease of use for beginner to intermediate programmers. The order methods are wrapped in a convenience layer that allows you to focus on your system's trading rules, leaving the underlying mechanics of order management and the relationships between entry orders, exit orders, and positions to **NinjaTrader**. This approach is best suited for simple to moderate order complexity, and can be further broken down into a Basic/Common Managed approach and a more [Advanced](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) Managed approach. The following section will discuss the use of the Basic/Common approach.

A few key points to keep in mind:

- Orders are submitted as live and working when a strategy is running in real-time

- Profit target, stop loss and trail stop orders are submitted immediately when an entry order is filled, and are tied together via OCO (One Cancels Other)

- Order changes and cancellations are queued in the event that the order is in a state where it can't be cancelled or modified

- By default, orders submitted via **Entry()** and **Exit()** methods automatically cancel at the end of a bar if not re-submitted

- **Entry()** methods will reverse the position automatically. For example if you are in a 1 contract long position and now call **EnterShort()** -\> you will see 2 executions, one to close the prior long position and the other to get you into the desired 1 contract short position.

- Via the [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) , [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) , [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) and [SetParabolicStop](https://developer.ninjatrader.com/docs/desktop/setparabolicstop) methods


## [Order submission for entry and exit methods - basic operation](https://developer.ninjatrader.com/docs/desktop/managed_approach\#order-submission-for-entry-and-exit-methods---basic-operation)

## Note

- Orders are primarily submitted from within the **OnBarUpdate()** method when a specific order method is called. By default, orders are kept alive, provided they are re-submitted on each call of the **OnBarUpdate()** method. If an order is not re-submitted, it is then canceled. Orders can be modified by re-submitting them with changed parameters (a new limit price, for example). In the example below, a Buy Limit order is working at the bid price, provided that the Close price of the current bar is greater than the current value of the 20 period Simple Moving Average. If the entry condition is no longer true and the order is still active, it will be immediately canceled.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Entry condition
     if (Close[0] > SMA(20)[0])
         EnterLongLimit(GetCurrentBid());
}

```

This technique allows you the quickest and easiest order submission method suitable for programmers of all levels. Should you want to submit an order and not have to keep re-submitting it to keep it alive you can use an [advanced approach](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) reserved for experienced programmers, which includes an option to keep orders alive until specifically canceled in code.

## [Order Entry Methods](https://developer.ninjatrader.com/docs/desktop/managed_approach\#order-entry-methods)

## Note

- Order Entry Methods Order entry methods are used to submit orders of different types. Methods exist to submit Market, Market-if-Touched, Limit, Stop Market, and Stop Limit orders. See the order-entry method pages listed in the help guide table of contents under this page for more information on a specific method. Signal Names on Entry Methods You can optionally tag an entry order with a signal name. Signal names are used to identify executions resulting from the order on a chart and in performance reports. Market positions created from a tagged entry method are marked with the signal name which serves two purposes:
- Used to tie an exit method to a specific position
- Used to identify unique entries in a strategy Below is an example of placing a Market entry order and an associated Limit exit order, tied together by the signal name of the entry order.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (CurrentBar < 1) return;

   if (Close[0] > Close[1])
   {
       // Place a Market order to enter long
       EnterLong("longEntry");

       // Manually place a Profit Target 10 ticks above the current price, tied to the entry order's SignalName
       ExitLongLimit(Close[0] + (10 * TickSize), "longEntry");
   }
}

```

### Defining how Entry Methods are Processed in a Strategy

You can limit how many entry methods are processed by determining the maximum number of entries in a single direction across all entry methods, or across unique signal names. The following properties can be set in the Strategies window when adding a strategy to a chart or to the Strategies tab of the Control Center window.

- [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection) property - Sets the maximum number of entries in a single direction
- [EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling) property - Determines if EntriesPerDirection applies across all entries or for entries with specified signal names

The example code below illustrates how the above properties control the processing of entry methods. The code contains two entry conditions and two **EnterLong** methods, each tagged with unique signal names.

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
       EntriesPerDirection = 1;
       EntryHandling = EntryHandling.AllEntries;
   }
}

protected override void OnBarUpdate()
{
   // Entry condition 1
   if (CrossAbove(SMA(10), SMA(20), 1))
       EnterLong("Condition 1 Entry");

   // Entry condition 2
   if (CrossAbove(RSI(14, 3), 30, 1))
       EnterLong("Condition 2 Entry");
}

```

### Entry Methods on Multi-Instrument Strategies

When running strategies that submit orders to multiple instruments, entry methods will submit orders to the instrument referenced by the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress). The following example assumes that the strategy is running on a 1 minute E-Mini S&P 500 chart. It adds an NQ data series, then enters a position on both instruments.

```jsx-150469391 csharp
protected override void OnStateChange()
{
     AddDataSeries("NQ 09-14", BarsPeriodType.Minute, 1);
}

protected override void OnBarUpdate()
{
     if (BarsInProgress == 0)
         EnterLong("ES Trade");
     else if (BarsInProgress == 1)
         EnterLong("NQ Trade");
}

```

More information on using BarsInProgress to filter instruments can be found in the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) page.

## [Quantity Type and TIF](https://developer.ninjatrader.com/docs/desktop/managed_approach\#quantity-type-and-tif)

You can set the entry order quantity and order type directly in code via the following properties:

- QuantityType - Sets the order quantity is taken from the entry method quantity property or the default strategy quantity size
- [TimeInForce](https://developer.ninjatrader.com/docs/desktop/timeinforce) property - Sets the time in force of the order

## [How to close a position](https://developer.ninjatrader.com/docs/desktop/managed_approach\#how-to-close-a-position)

- Closing a Position using a Stop Loss, Trailing Stop and/or Profit Target You can predefine a stop loss, trailing stop and/or profit target in a strategy by calling the [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss), [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) and/or [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) methods from inside the **OnStateChange()** event handler. When these methods are called, they submit live working orders in real-time as executions are reported as a result of calling an entry method. These orders are also tied via OCO (One Cancels Other). Stop losses and profit target can be generated for each fill or each position. This is determined by the "Stop & target submission" property which is set in the Strategies window. Possible values are listed below:
- ByStrategyPosition - When this is selected, only one stop loss, trail stop and/or profit target order is submitted. As entry executions come in, the order size is amended. The downside of this approach is that if you receive partial fills, the orders are re-inserted into the exchange order queue. The upside is that if you broker charges you commission per order (not per quantity), you will not incur additional commission expenses.
- PerEntryExecution - When this is selected, a stop loss, trail stop and/or profit target order is submitted for each partial fill received. The downside is that if your broker charges commission per order, you can incur very expensive commission costs if you receive partial fills. The upside is that orders are submitted as soon as possible, giving you the advantage of getting into the order queue immediately.

### Closing a Position using an Exit Method

Exit methods submit orders to close out a position in whole or in part. When closing a position with Exit orders, the order quantity will be reduced as the strategy position reduces - for example, if we use [ExitLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitlongstopmarket) and [ExitLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitlongstoplimit) to protect a position and one of those orders gets filled, the other order associated with exiting that position will reduce their quantity.

As with entry methods, more information about specific exit methods can be found in this Help Guide's table of contents, beneath this page.

### Closing a Partial Position using an Exit Method

You can close out a partial position by specifying the exit quantity. The following example first enters long for three contracts. Then, each subsequent bar update submits a market order to exit one contract until the position is completely closed. "ExitLong(1)" will be ignored if a long market position does not exist.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1))
         EnterLong(3);

     ExitLong(1);
}

```

FromEntrySignal -- Using Signal Names in Exit Methods

Identifying entries with a signal name allows you to place multiple unique entries within a single strategy and call exit methods with specified signal names, so that only a position created with the specified signal name is closed. In the example below, there are two entry conditions which create positions, and two exit conditions specifying which position to close based on the signal name.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Entry condition 1
     if (CrossAbove(SMA(10), SMA(20), 1))
         EnterLong("Condition 1 Entry");

     // Entry condition 2
     if (CrossAbove(RSI(14, 3), 30, 1))
         EnterLong("Condition 2 Entry");

     // Closes the position created by entry condition 1
     if (CrossBelow(SMA(10), SMA(20), 1))
         ExitLong("Condition 1 Entry");

     // Closes the position created by entry condition 2
     if (CrossBelow(RSI(14, 3), 70, 1))
         ExitLong("Condition 2 Entry");

```

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (Position.MarketPosition == MarketPosition.Flat)
   {
       // Entry condition 1
       if (CrossAbove(SMA(10), SMA(20), 1))
           EnterLong("Condition 1 Entry");
   }

   if (Position.MarketPosition != MarketPosition.Flat)
   {
       // Scale in condition 2 for position management
       if (CrossAbove(RSI(14, 3), 30, 1))
           EnterLong("Condition 2 Entry");

       // Exit all positions using an empty string (could also use string.Empty)
       if (CrossBelow(SMA(10), SMA(20), 1))
           ExitLong("Exit All", "");
   }
}

```

## [Understanding core order objects](https://developer.ninjatrader.com/docs/desktop/managed_approach\#understanding-core-order-objects)

- When using order methods such as [EnterLong()](https://developer.ninjatrader.com/docs/desktop/enterlong), [ExitShortLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortlimit), etc, a direct [order object](https://developer.ninjatrader.com/docs/desktop/order) is returned for the **NinjaTrader** Core. These objects can be used throughout the lifetime of your strategy to provide additional metadata concerning your strategy, as well as apply advanced concepts such as [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/cancelorder) and [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder). More information about this advanced concept which is discussed under the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Internal Order Handling Rules that Reduce Unwanted Positions](https://developer.ninjatrader.com/docs/desktop/managed_approach\#internal-order-handling-rules-that-reduce-unwanted-positions)

- To prevent situations in real-time in which you may have multiple orders working to accomplish the same task, there are some "under the hood" rules that a **NinjaScript** strategy follows when Managed order methods are called. For example, if your strategy had a limit order for 1 contract working as a Profit Target, but then your strategy was also programmed to reverse the position at the price very close to the target limit order, then submitting both orders can be risky, since it could lead to a larger position than the strategy is designed to enter if both orders got filled in quick succession by the exchange.

The following rules are true per unique signal name:

Methods that generate orders to enter a position will be ignored if:

- A position is open and an order submitted by a non market order exit method ( [ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a set method ( [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) for example) is active and the order is used to open a position in the opposite direction
- A position is open and two or more Entry methods to reverse the position are entered together. In this case the second Entry order will be ignored.
- The strategy position is flat and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- The entry signal name is not unique

Methods that generate orders to exit a position will be ignored if:

- A position is open and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a set method ( [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss) for example) is active

Set() methods that generate orders to exit a position will be ignored if:

- A position is open and an order submitted by an enter method ( [EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit) for example) is active and the order is used to open a position in the opposite direction
- A position is open and an order submitted by a non market order exit method ( [ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit) for example) is active