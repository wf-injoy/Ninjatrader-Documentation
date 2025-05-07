## [Definition](https://developer.ninjatrader.com/docs/desktop/performanceunit\#definition)

Enumeration defining each type of **PerformanceUnit** calculated by **NinjaTrader**. Used to store a value for this performance type in **PerformanceMetrics**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/performanceunit\#syntax)

`PerformanceUnit.Currency`

`PerformanceUnit.Percent`

`PerformanceUnit.Pips`

`PerformanceUnit.Points`

`PerformanceUnit.Ticks`

## [Examples](https://developer.ninjatrader.com/docs/desktop/performanceunit\#examples)

```jsx-150469391 csharp
//Prints unrealized PnL in ticks at the close of each bar
Print(Position.GetUnrealizedProfitLoss(PerformanceUnit.Ticks, Close[0]));

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/performanceunit\#definition)

Enumeration defining each type of **PerformanceUnit** calculated by **NinjaTrader**. Used to store a value for this performance type in **PerformanceMetrics**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/performanceunit\#syntax)

`PerformanceUnit.Currency`

`PerformanceUnit.Percent`

`PerformanceUnit.Pips`

`PerformanceUnit.Points`

`PerformanceUnit.Ticks`

## [Examples](https://developer.ninjatrader.com/docs/desktop/performanceunit\#examples)

```jsx-150469391 csharp
//Prints unrealized PnL in ticks at the close of each bar
Print(Position.GetUnrealizedProfitLoss(PerformanceUnit.Ticks, Close[0]));

```