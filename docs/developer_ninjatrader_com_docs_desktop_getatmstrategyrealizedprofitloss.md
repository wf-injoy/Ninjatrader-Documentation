## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#definition)

Gets the realized profit and loss value of the specified ATM Strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#method-return-value)

A **double** value representing the realized profit and loss.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#syntax)

`GetAtmStrategyRealizedProfitLoss(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     Print("PnL is " + GetAtmStrategyRealizedProfitLoss("id").ToString());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#definition)

Gets the realized profit and loss value of the specified ATM Strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#method-return-value)

A **double** value representing the realized profit and loss.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#syntax)

`GetAtmStrategyRealizedProfitLoss(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyrealizedprofitloss\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     Print("PnL is " + GetAtmStrategyRealizedProfitLoss("id").ToString());
}

```