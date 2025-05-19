## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#definition)

Changes the price of the specified order of the specified ATM strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#syntax)

`AtmStrategyChangeStopTarget(double limitPrice, double stopPrice, string orderName, string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#parameters)

| limitPrice | Order limit price |
| stopPrice | Order stop price |
| orderName | The order name such as "Stop1" or "Target2" |
| atmStrategyId | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     AtmStrategyChangeStopTarget(0, SMA(10)[0], "Stop1", "AtmIdValue");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#definition)

Changes the price of the specified order of the specified ATM strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#method-return-value)

Returns true if the specified order was found; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#syntax)

`AtmStrategyChangeStopTarget(double limitPrice, double stopPrice, string orderName, string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#parameters)

| limitPrice | Order limit price |
| stopPrice | Order stop price |
| orderName | The order name such as "Stop1" or "Target2" |
| atmStrategyId | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategychangestoptarget\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     AtmStrategyChangeStopTarget(0, SMA(10)[0], "Stop1", "AtmIdValue");
}

```