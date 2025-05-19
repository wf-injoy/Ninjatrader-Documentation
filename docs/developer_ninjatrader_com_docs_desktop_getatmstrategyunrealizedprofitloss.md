## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#definition)

Gets the unrealized profit and loss value of the specified ATM Strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#method-return-value)

A **double** value representing the unrealized profit and loss.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#syntax)

`GetAtmStrategyUnrealizedProfitLoss(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     Print("Unrealized PnL is " + GetAtmStrategyUnrealizedProfitLoss("id").ToString());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#definition)

Gets the unrealized profit and loss value of the specified ATM Strategy.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#method-return-value)

A **double** value representing the unrealized profit and loss.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#syntax)

`GetAtmStrategyUnrealizedProfitLoss(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategyunrealizedprofitloss\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     Print("Unrealized PnL is " + GetAtmStrategyUnrealizedProfitLoss("id").ToString());
}

```