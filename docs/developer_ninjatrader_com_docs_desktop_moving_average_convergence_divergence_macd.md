## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#description)

MACD uses moving averages, which are lagging indicators, to include some trend-following characteristics. These lagging indicators are turned into a momentum oscillator by subtracting the longer moving average from the shorter moving average.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_MACD1.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#syntax)

`MACD(int fast, int slow, int smooth)`

`MACD(ISeries<double> input, int fast, int slow, int smooth)`

**Returns MACD value**

`MACD(int fast, int slow, int smooth)[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

**Returns average value**

`MACD(int fast, int slow, int smooth).Avg[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth).Avg[int barsAgo]`

**Returns difference value**

`MACD(int fast, int slow, int smooth).Diff[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth).Diff[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#parameters)

| fast | The number of bars to calculate the fast [**EMA**](https://developer.ninjatrader.com/docs/desktop/moving_average_exponential_ema) |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The numbers of bars to calculate the slow EMA |
| smooth | The number of bars to calculate the EMA signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#examples)

```jsx-150469391 csharp
// Prints the current MACD value
double value = MACD(12, 26, 9)[0];
Print("The current MACD value is " + value.ToString());

// Prints the current MACD average value
double value = MACD(12, 26, 9).Avg[0];
Print("The current MACD average value is " + value.ToString());

// Prints the current MACD difference value
double value = MACD(12, 26, 9).Diff[0];
Print("The current MACD difference value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#description)

MACD uses moving averages, which are lagging indicators, to include some trend-following characteristics. These lagging indicators are turned into a momentum oscillator by subtracting the longer moving average from the shorter moving average.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_MACD1.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#syntax)

`MACD(int fast, int slow, int smooth)`

`MACD(ISeries<double> input, int fast, int slow, int smooth)`

**Returns MACD value**

`MACD(int fast, int slow, int smooth)[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

**Returns average value**

`MACD(int fast, int slow, int smooth).Avg[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth).Avg[int barsAgo]`

**Returns difference value**

`MACD(int fast, int slow, int smooth).Diff[int barsAgo]`

`MACD(ISeries<double> input, int fast, int slow, int smooth).Diff[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#parameters)

| fast | The number of bars to calculate the fast [**EMA**](https://developer.ninjatrader.com/docs/desktop/moving_average_exponential_ema) |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The numbers of bars to calculate the slow EMA |
| smooth | The number of bars to calculate the EMA signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#examples)

```jsx-150469391 csharp
// Prints the current MACD value
double value = MACD(12, 26, 9)[0];
Print("The current MACD value is " + value.ToString());

// Prints the current MACD average value
double value = MACD(12, 26, 9).Avg[0];
Print("The current MACD average value is " + value.ToString());

// Prints the current MACD difference value
double value = MACD(12, 26, 9).Diff[0];
Print("The current MACD difference value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_convergence_divergence_macd\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.