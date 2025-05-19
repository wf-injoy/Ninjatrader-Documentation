## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#description)

The Chaikin Oscillator is simply the Moving Average Convergence Divergence indicator (MACD) applied to the Accumulation/Distribution Line. The formula is the difference between the 3-day exponential moving average and the 10-day exponential moving average of the Accumulation/Distribution Line. Just as the MACD-Histogram is an indicator to predict moving average crossovers in MACD, the Chaikin Oscillator is an indicator to predict changes in the Accumulation/Distribution Line.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/chaikin-oscillator)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#syntax)

`ChaikinOscillator(int fast, int slow)`

`ChaikinOscillator(ISeries<double> input, int fast, int slow)`

**Returns default value**

`ChaikinOscillator(int fast, int slow)[int barsAgo]`

`ChaikinOscillator**[ISeries<double> input, int fast, int slow](int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#parameters)

| fast | input | slow |
| --- | --- | --- |
| The number of bars to calculate the fast **EMA** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | The number of bars to calculate the slow **EMA** |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current value of a ChaikinOscillator using default price type
double value = ChaikinOscillator(3, 10)[0];
Print("The current ChaikinOscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#description)

The Chaikin Oscillator is simply the Moving Average Convergence Divergence indicator (MACD) applied to the Accumulation/Distribution Line. The formula is the difference between the 3-day exponential moving average and the 10-day exponential moving average of the Accumulation/Distribution Line. Just as the MACD-Histogram is an indicator to predict moving average crossovers in MACD, the Chaikin Oscillator is an indicator to predict changes in the Accumulation/Distribution Line.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/chaikin-oscillator)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#syntax)

`ChaikinOscillator(int fast, int slow)`

`ChaikinOscillator(ISeries<double> input, int fast, int slow)`

**Returns default value**

`ChaikinOscillator(int fast, int slow)[int barsAgo]`

`ChaikinOscillator**[ISeries<double> input, int fast, int slow](int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#parameters)

| fast | input | slow |
| --- | --- | --- |
| The number of bars to calculate the fast **EMA** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | The number of bars to calculate the slow **EMA** |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current value of a ChaikinOscillator using default price type
double value = ChaikinOscillator(3, 10)[0];
Print("The current ChaikinOscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.