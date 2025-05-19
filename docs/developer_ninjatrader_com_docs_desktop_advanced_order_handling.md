Advanced order handling is reserved for EXPERIENCED programmers. Through advanced order handling you can submit, change and cancel orders at your discretion through any event-driven method within a strategy. Each order method within the "Managed Approach" section has a method overload designed for advanced handling.

## Note

Orders can remain live until you call the **CancelOrder()** method, or until the order's time in force has expired, whichever comes first. This flexibility allows you to control exactly when an order should be cancelled instead of relying on the close of a bar. Each order method, such as **EnterLongLimit()**, has a method overload designed to submit a "live until canceled" order. When using this overload, it is important to retain a reference to the Order object, so that it can be canceled via CancelOrder() at a later time.

All order methods return an **Order** object. There are several important items to note:

- An Order object returned from calling an order method contains dynamic properties which will always reflect the current state of the associated order
- The property **order.OrderId** is NOT a unique value, since it can change throughout an order's lifetime. Please see the section below on "Transitioning order references from historical to live" for details on how to handle.
- To check for equality, you can compare Order objects directly

The following example code demonstrates the submission of an order and the assignment of the Order return object to the variable "entryOrder." After this, the object is checked in the OnOrderUpdate() method for equality, and then checked for the Filled state.

```jsx-150469391 csharp
private Order entryOrder = null;
protected override void OnBarUpdate()
{
     if (entryOrder == null && Close[0] > Open[0])
         EnterLong("myEntryOrder");
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
     // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
     // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not gauranteed to be complete if it is referenced immediately after submitting
     if (order.Name == "myEntryOrder" && orderState != OrderState.Filled)
       entryOrder = order;

   // Null Entry order if filled or cancelled. We do not use the Order objects after the order is filled, so we can null it here
   if (entryOrder != null && entryOrder == order)
    {
       if (order.OrderState == OrderState.Cancelled && order.Filled == 0)
           entryOrder = null;
       if (order.OrderState == OrderState.Filled)
           entryOrder = null;
    }
}

```

## [Transitioning order references from historical to live](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#transitioning-order-references-from-historical-to-live)

When starting a strategy on real-time data, the [starting behavior](https://ninjatrader.com/support/helpguides/nt8/?syncing_account_positions.htm) will renew any active historical orders and resubmit these orders to your live or simulation account.  This process includes updating the historical/backtest generated order ID to the account generated order ID, and any associated OCO IDs.  If you are tracking order objects, is critical that you update the order reference to ensure that it is now using the correct order details.

This should be done in [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) to ensure all cases of order transitions are handled.

```jsx-150469391 csharp
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
}

```

## [Working with a Multi-Instrument Strategy](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#working-with-a-multi-instrument-strategy)

With advanced order handling, you can submit an order in the context of any [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object by designating the "BarsInProgress" index. For example, if your primary bar series is "MSFT" and your secondary series added to the strategy through the AddDataSeries() method is "AAPL", you can submit an order for either "MSFT" or "AAPL" from anywhere within the strategy. In addition to the information found in the [multi-time frame and instrument strategies](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) page, this section specifically covers order submission.

As an example, consider the EnterLongLimit() method and one of its method overloads designed for advanced order handling:

`EnterLongLimit(int barsInProgressIndex, bool isLiveUntilCancelled, int quantity, double limitPrice, string signalName)`

In this example, an "MSFT 1 minute" chart is the primary bar series on which the strategy is running. A secondary bar series is added for "AAPL 1 minute" via the AddDataSeries() method in the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) event handler. After adding the secondary Bars object, MSFT has a [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) index of 0 and AAPL has an index value of 1.

The following example code demonstrates how to monitor for bar update events on the first instrument, while submitting orders to the second instrument.

## [Examples](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#examples)

```jsx-150469391 csharp
private Order entryOrder = null;

protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      AddDataSeries("AAPL", BarsPeriodType.Minute, 1);
  }
}

protected override void OnBarUpdate()
{
    // Check if the MSFT series triggered an bar update event
    if (BarsInProgress == 0)
    {
        // Submit an order for AAPL in the context of MSFT bar update event
        if (entryOrder == null)
              EnterLongLimit(1, true, 1, Lows[1][0], "AAPL Order");
    }
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
    // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not gauranteed to be complete if it is referenced immediately after submitting
    if (order.Name == "AAPL Order" && orderState != OrderState.Filled)
      entryOrder = order;
}

```

Advanced order handling is reserved for EXPERIENCED programmers. Through advanced order handling you can submit, change and cancel orders at your discretion through any event-driven method within a strategy. Each order method within the "Managed Approach" section has a method overload designed for advanced handling.

## Note

Orders can remain live until you call the **CancelOrder()** method, or until the order's time in force has expired, whichever comes first. This flexibility allows you to control exactly when an order should be cancelled instead of relying on the close of a bar. Each order method, such as **EnterLongLimit()**, has a method overload designed to submit a "live until canceled" order. When using this overload, it is important to retain a reference to the Order object, so that it can be canceled via CancelOrder() at a later time.

All order methods return an **Order** object. There are several important items to note:

- An Order object returned from calling an order method contains dynamic properties which will always reflect the current state of the associated order
- The property **order.OrderId** is NOT a unique value, since it can change throughout an order's lifetime. Please see the section below on "Transitioning order references from historical to live" for details on how to handle.
- To check for equality, you can compare Order objects directly

The following example code demonstrates the submission of an order and the assignment of the Order return object to the variable "entryOrder." After this, the object is checked in the OnOrderUpdate() method for equality, and then checked for the Filled state.

```jsx-150469391 csharp
private Order entryOrder = null;
protected override void OnBarUpdate()
{
     if (entryOrder == null && Close[0] > Open[0])
         EnterLong("myEntryOrder");
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
     // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
     // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not gauranteed to be complete if it is referenced immediately after submitting
     if (order.Name == "myEntryOrder" && orderState != OrderState.Filled)
       entryOrder = order;

   // Null Entry order if filled or cancelled. We do not use the Order objects after the order is filled, so we can null it here
   if (entryOrder != null && entryOrder == order)
    {
       if (order.OrderState == OrderState.Cancelled && order.Filled == 0)
           entryOrder = null;
       if (order.OrderState == OrderState.Filled)
           entryOrder = null;
    }
}

```

## [Transitioning order references from historical to live](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#transitioning-order-references-from-historical-to-live)

When starting a strategy on real-time data, the [starting behavior](https://ninjatrader.com/support/helpguides/nt8/?syncing_account_positions.htm) will renew any active historical orders and resubmit these orders to your live or simulation account.  This process includes updating the historical/backtest generated order ID to the account generated order ID, and any associated OCO IDs.  If you are tracking order objects, is critical that you update the order reference to ensure that it is now using the correct order details.

This should be done in [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/onorderupdate) to ensure all cases of order transitions are handled.

```jsx-150469391 csharp
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
}

```

## [Working with a Multi-Instrument Strategy](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#working-with-a-multi-instrument-strategy)

With advanced order handling, you can submit an order in the context of any [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object by designating the "BarsInProgress" index. For example, if your primary bar series is "MSFT" and your secondary series added to the strategy through the AddDataSeries() method is "AAPL", you can submit an order for either "MSFT" or "AAPL" from anywhere within the strategy. In addition to the information found in the [multi-time frame and instrument strategies](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) page, this section specifically covers order submission.

As an example, consider the EnterLongLimit() method and one of its method overloads designed for advanced order handling:

`EnterLongLimit(int barsInProgressIndex, bool isLiveUntilCancelled, int quantity, double limitPrice, string signalName)`

In this example, an "MSFT 1 minute" chart is the primary bar series on which the strategy is running. A secondary bar series is added for "AAPL 1 minute" via the AddDataSeries() method in the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) event handler. After adding the secondary Bars object, MSFT has a [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) index of 0 and AAPL has an index value of 1.

The following example code demonstrates how to monitor for bar update events on the first instrument, while submitting orders to the second instrument.

## [Examples](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling\#examples)

```jsx-150469391 csharp
private Order entryOrder = null;

protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      AddDataSeries("AAPL", BarsPeriodType.Minute, 1);
  }
}

protected override void OnBarUpdate()
{
    // Check if the MSFT series triggered an bar update event
    if (BarsInProgress == 0)
    {
        // Submit an order for AAPL in the context of MSFT bar update event
        if (entryOrder == null)
              EnterLongLimit(1, true, 1, Lows[1][0], "AAPL Order");
    }
}

protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
    // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not gauranteed to be complete if it is referenced immediately after submitting
    if (order.Name == "AAPL Order" && orderState != OrderState.Filled)
      entryOrder = order;
}

```