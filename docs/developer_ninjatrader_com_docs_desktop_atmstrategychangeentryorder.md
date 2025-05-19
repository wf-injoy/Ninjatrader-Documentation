## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#definition)

Changes the price of the specified entry order.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#syntax)

`AtmStrategyChangeEntryOrder(double limitPrice, double stopPrice, string orderId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#parameters)

| limitPrice | Order limit price |
| stopPrice | Order stop price |
| orderId | The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     AtmStrategyChangeEntryOrder(GetCurrentBid(), 0, "orderIdValue");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#definition)

Changes the price of the specified entry order.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#syntax)

`AtmStrategyChangeEntryOrder(double limitPrice, double stopPrice, string orderId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#parameters)

| limitPrice | Order limit price |
| stopPrice | Order stop price |
| orderId | The unique identifier for the entry order |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategychangeentryorder\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     AtmStrategyChangeEntryOrder(GetCurrentBid(), 0, "orderIdValue");
}

```