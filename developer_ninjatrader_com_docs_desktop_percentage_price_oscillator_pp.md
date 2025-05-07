## [Description](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#description)

The Percentage Price Oscillator shows the percentage difference between two **exponential moving averages**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#syntax)

`PPO(int fast, int slow, int smooth)`

`PPO(ISeries<double> input, int fast, int slow, int smooth)`

**Returns default value**

`PPO(int fast, int slow, int smooth)[int barsAgo]`

`PPO(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

**Returns smoothed value**

`PPO(int fast, int slow, int smooth).Smoothed[int barsAgo]`

`PPO(ISeries<double> input, int fast, int slow, int smooth).Smoothed[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#parameters)

| fast | The number of bars to calculate the fast EMA |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The number of bars to calculate the slow EMA |
| smooth | The number of bars to calculate the EMA signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period Percentage Price Oscillator
double value = PPO(12, 26, 9)[0];
Print("The current Percentage Price Oscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#description)

The Percentage Price Oscillator shows the percentage difference between two **exponential moving averages**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#syntax)

`PPO(int fast, int slow, int smooth)`

`PPO(ISeries<double> input, int fast, int slow, int smooth)`

**Returns default value**

`PPO(int fast, int slow, int smooth)[int barsAgo]`

`PPO(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

**Returns smoothed value**

`PPO(int fast, int slow, int smooth).Smoothed[int barsAgo]`

`PPO(ISeries<double> input, int fast, int slow, int smooth).Smoothed[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#parameters)

| fast | The number of bars to calculate the fast EMA |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The number of bars to calculate the slow EMA |
| smooth | The number of bars to calculate the EMA signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period Percentage Price Oscillator
double value = PPO(12, 26, 9)[0];
Print("The current Percentage Price Oscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/percentage_price_oscillator_pp\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.