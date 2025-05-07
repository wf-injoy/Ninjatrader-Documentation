## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#definition)

Cancels the specified entry order determined by the string "orderId" parameter.

## Note

1. This method is intended ONLY for orders submitted as [Atm Entry Orders](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) and assumes the [OrderState](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus) is NOT terminal (i.e., Cancelled, Filled, Rejected, Unknown).
2. If the specified order does not exist, the method returns false and an error is logged.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#syntax)

`AtmStrategyCancelEntryOrder(string orderId)`

## Warning

This method should ONLY be called once the strategy [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Realtime

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#parameters)

| orderId |
| --- |
| The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // ATM strategy methods only work during real-time
   if (State != State.Realtime)
     return;

   string[] entryOrder = GetAtmStrategyEntryOrderStatus("orderId");

   // checks if the entry order exists
   // and the order state is not already cancelled/filled/rejected
   if (entryOrder.Length > 0 && entryOrder[2] == "Working")
   {
     AtmStrategyCancelEntryOrder("orderId");
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#definition)

Cancels the specified entry order determined by the string "orderId" parameter.

## Note

1. This method is intended ONLY for orders submitted as [Atm Entry Orders](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) and assumes the [OrderState](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus) is NOT terminal (i.e., Cancelled, Filled, Rejected, Unknown).
2. If the specified order does not exist, the method returns false and an error is logged.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#syntax)

`AtmStrategyCancelEntryOrder(string orderId)`

## Warning

This method should ONLY be called once the strategy [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Realtime

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#parameters)

| orderId |
| --- |
| The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategycancelentryorder\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // ATM strategy methods only work during real-time
   if (State != State.Realtime)
     return;

   string[] entryOrder = GetAtmStrategyEntryOrderStatus("orderId");

   // checks if the entry order exists
   // and the order state is not already cancelled/filled/rejected
   if (entryOrder.Length > 0 && entryOrder[2] == "Working")
   {
     AtmStrategyCancelEntryOrder("orderId");
   }
}

```