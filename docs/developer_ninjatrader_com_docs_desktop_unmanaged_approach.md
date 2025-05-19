The Unmanaged approach is reserved for VERY EXPERIENCED programmers. In place of the convenience layer that the [Managed](https://developer.ninjatrader.com/docs/desktop/managed_approach) approach offered, the Unmanaged approach instead offers ultimate flexibility in terms of order submission and management. This section will discuss some of the basics of working with Unmanaged order methods.

## [Getting started with Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#getting-started-with-unmanaged-order-methods)

To be able to offer you the flexibility required to achieve more complex order submission techniques, NinjaTrader needs to be able to know if you are going to be using the Unmanaged approach beforehand.

In the OnStateChange() method designating the [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) property as true signifies to NinjaTrader that you will be using the Unmanaged approach. Setting this will effectively prevent any of the signal tracking and internal order handling rules that were present in the Managed approach.

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        IsUnmanaged = true;
    }
}

```

Please note that you will not be able to mix order methods from the two approaches. When setting [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) to true, you can only use Unmanaged order methods in the strategy.

## [Working with Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#working-with-unmanaged-order-methods)

## [Order Submission](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-submission)

Order submission with the Unmanaged approach is done solely from a single order method. Parameterizing the [SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged) method differently will determine what kind of order you will be submitting. Please note that these orders are live until cancelled. Should you want to cancel these orders you will need to use the CancelOrder() method or wait till the orders expire due to the strategy's time in force setting.

In the example below, a buy limit order to enter a long position is working at the bid price provided that the close price of the current bar is greater than the current value of the 20 period simple moving average.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Entry condition
    if (Close[0] > SMA(20)[0] && entryOrder == null)
        entryOrder = SubmitOrderUnmanaged(0, OrderAction.Buy, OrderType.Limit, 1, GetCurrentBid(), 0, "", "Long Limit");
}

```

It is critical to assign an [Order](https://developer.ninjatrader.com/docs/desktop/order) object to keep track of your order or else you will not be able to identify it in your code later since there is no signal tracking when using Unmanaged order methods. Please be aware of the following information about Order objects:

•An Order object returned from calling an order method is dynamic in that its properties will always reflect the current state of an order

•The property < `Order` >.OrderId is NOT a unique value since it can change throughout an order's lifetime

•To check for equality you can compare Order objects directly

## [Order Modification](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-modification)

Unlike the Managed approach where you could modify a working order by calling the entry order method again with your new parameters, the Unmanaged approach requires the utilization of the [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder) method. The ChangeOrder() method requires you to have access to the Order object you wish to modify so it is important to hold onto those for any active order you have in your strategy.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
	// Raise stop loss to breakeven when you are at least 4 ticks in profit
	if (stopOrder != null && stopOrder.StopPrice < Position.AveragePrice && Close[0] >= Position.AveragePrice + 4 * TickSize)
	  ChangeOrder(stopOrder, stopOrder.Quantity, 0, Position.AveragePrice);
}

```

## [Order Cancellation](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-cancellation)

Similar to the live until canceled technique from the Managed approach, canceling orders can be done through the [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder) method.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Cancel entry order if price is moving away from our limit price
    if (entryOrder != null && Close[0] < entryOrder.LimitPrice - 4 * TickSize)
    {
        CancelOrder(entryOrder);

        // If the entryOrder Order object is no longer needed I should reset it to null in the OnOrderUpdate() method
    }
}

```

## [Signal Tracking](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#signal-tracking)

Since the Unmanaged approach does not utilize NinjaScript's signal tracking the features associated with it will no longer be relevant. The following properties and their associated concept cannot be used with Unmanaged order methods:

[EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection)

[EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling)

[SetOrderQuantity](https://developer.ninjatrader.com/docs/desktop/setorderquantity)

Methods utilizing signal names like [BarsSinceEntryExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceentryexecution) and [BarsSinceExitExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution) can still be used though.

## [Critical considerations when using Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#critical-considerations-when-using-unmanaged-order-methods)

|  |  |
| --- | --- |
| [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder) | Cancels a specified order. |
| [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_changeorder) | Amends a specified [Order](https://developer.ninjatrader.com/docs/desktop/order). |
| [IgnoreOverfill](https://developer.ninjatrader.com/docs/desktop/ignoreoverfill) | An [unmanaged order property](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach) which defines the behavior of a strategy when an overfill is detected. |
| [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) | Determines if the strategy will be using Unmanaged order methods. |
| [SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged) | Generates an [Unmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) order. |

The Unmanaged approach is reserved for VERY EXPERIENCED programmers. In place of the convenience layer that the [Managed](https://developer.ninjatrader.com/docs/desktop/managed_approach) approach offered, the Unmanaged approach instead offers ultimate flexibility in terms of order submission and management. This section will discuss some of the basics of working with Unmanaged order methods.

## [Getting started with Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#getting-started-with-unmanaged-order-methods)

To be able to offer you the flexibility required to achieve more complex order submission techniques, NinjaTrader needs to be able to know if you are going to be using the Unmanaged approach beforehand.

In the OnStateChange() method designating the [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) property as true signifies to NinjaTrader that you will be using the Unmanaged approach. Setting this will effectively prevent any of the signal tracking and internal order handling rules that were present in the Managed approach.

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        IsUnmanaged = true;
    }
}

```

Please note that you will not be able to mix order methods from the two approaches. When setting [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) to true, you can only use Unmanaged order methods in the strategy.

## [Working with Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#working-with-unmanaged-order-methods)

## [Order Submission](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-submission)

Order submission with the Unmanaged approach is done solely from a single order method. Parameterizing the [SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged) method differently will determine what kind of order you will be submitting. Please note that these orders are live until cancelled. Should you want to cancel these orders you will need to use the CancelOrder() method or wait till the orders expire due to the strategy's time in force setting.

In the example below, a buy limit order to enter a long position is working at the bid price provided that the close price of the current bar is greater than the current value of the 20 period simple moving average.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Entry condition
    if (Close[0] > SMA(20)[0] && entryOrder == null)
        entryOrder = SubmitOrderUnmanaged(0, OrderAction.Buy, OrderType.Limit, 1, GetCurrentBid(), 0, "", "Long Limit");
}

```

It is critical to assign an [Order](https://developer.ninjatrader.com/docs/desktop/order) object to keep track of your order or else you will not be able to identify it in your code later since there is no signal tracking when using Unmanaged order methods. Please be aware of the following information about Order objects:

•An Order object returned from calling an order method is dynamic in that its properties will always reflect the current state of an order

•The property < `Order` >.OrderId is NOT a unique value since it can change throughout an order's lifetime

•To check for equality you can compare Order objects directly

## [Order Modification](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-modification)

Unlike the Managed approach where you could modify a working order by calling the entry order method again with your new parameters, the Unmanaged approach requires the utilization of the [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder) method. The ChangeOrder() method requires you to have access to the Order object you wish to modify so it is important to hold onto those for any active order you have in your strategy.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
	// Raise stop loss to breakeven when you are at least 4 ticks in profit
	if (stopOrder != null && stopOrder.StopPrice < Position.AveragePrice && Close[0] >= Position.AveragePrice + 4 * TickSize)
	  ChangeOrder(stopOrder, stopOrder.Quantity, 0, Position.AveragePrice);
}

```

## [Order Cancellation](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#order-cancellation)

Similar to the live until canceled technique from the Managed approach, canceling orders can be done through the [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder) method.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Cancel entry order if price is moving away from our limit price
    if (entryOrder != null && Close[0] < entryOrder.LimitPrice - 4 * TickSize)
    {
        CancelOrder(entryOrder);

        // If the entryOrder Order object is no longer needed I should reset it to null in the OnOrderUpdate() method
    }
}

```

## [Signal Tracking](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#signal-tracking)

Since the Unmanaged approach does not utilize NinjaScript's signal tracking the features associated with it will no longer be relevant. The following properties and their associated concept cannot be used with Unmanaged order methods:

[EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection)

[EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling)

[SetOrderQuantity](https://developer.ninjatrader.com/docs/desktop/setorderquantity)

Methods utilizing signal names like [BarsSinceEntryExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceentryexecution) and [BarsSinceExitExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution) can still be used though.

## [Critical considerations when using Unmanaged order methods](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach\#critical-considerations-when-using-unmanaged-order-methods)

|  |  |
| --- | --- |
| [CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder) | Cancels a specified order. |
| [ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_changeorder) | Amends a specified [Order](https://developer.ninjatrader.com/docs/desktop/order). |
| [IgnoreOverfill](https://developer.ninjatrader.com/docs/desktop/ignoreoverfill) | An [unmanaged order property](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach) which defines the behavior of a strategy when an overfill is detected. |
| [IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) | Determines if the strategy will be using Unmanaged order methods. |
| [SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged) | Generates an [Unmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged) order. |