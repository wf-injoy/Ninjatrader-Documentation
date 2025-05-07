## [Definition](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#definition)

This method calculates the value for the Optimization Fitness.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#syntax)

`protected override void OnCalculatePerformanceValue(StrategyBase strategy)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#examples)

```jsx-150469391 csharp
protected override void OnCalculatePerformanceValue(StrategyBase strategy)
{

     Value = strategy.SystemPerformance.AllTrades.TradesPerformance.Percent.Drawdown;

}
```

## [Definition](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#definition)

This method calculates the value for the Optimization Fitness.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#syntax)

`protected override void OnCalculatePerformanceValue(StrategyBase strategy)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncalculateperformancevalue\#examples)

```jsx-150469391 csharp
protected override void OnCalculatePerformanceValue(StrategyBase strategy)
{

     Value = strategy.SystemPerformance.AllTrades.TradesPerformance.Percent.Drawdown;

}
```