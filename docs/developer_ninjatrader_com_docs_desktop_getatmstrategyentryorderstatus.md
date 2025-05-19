## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#definition)

Gets the current state of the specified entry order.

## Note

If the method can't find the specified order, an empty array is returned.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#method-return-value)

A string\[\] array holding three elements that represent average fill price, filled amount and order state.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#syntax)

`GetAtmStrategyEntryOrderStatus(string orderId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#parameters)

| **orderId** | The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     string[] entryOrder = GetAtmStrategyEntryOrderStatus("orderId");

     // Check length to ensure that returned array holds order information
     if (entryOrder.Length > 0)
     {
         Print("Average fill price is " + entryOrder[0].ToString());
         Print("Filled amount is " + entryOrder[1].ToString());
         Print("Current state is " + entryOrder[2].ToString());
     }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#definition)

Gets the current state of the specified entry order.

## Note

If the method can't find the specified order, an empty array is returned.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#method-return-value)

A string\[\] array holding three elements that represent average fill price, filled amount and order state.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#syntax)

`GetAtmStrategyEntryOrderStatus(string orderId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#parameters)

| **orderId** | The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyentryorderstatus\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     string[] entryOrder = GetAtmStrategyEntryOrderStatus("orderId");

     // Check length to ensure that returned array holds order information
     if (entryOrder.Length > 0)
     {
         Print("Average fill price is " + entryOrder[0].ToString());
         Print("Filled amount is " + entryOrder[1].ToString());
         Print("Current state is " + entryOrder[2].ToString());
     }

```