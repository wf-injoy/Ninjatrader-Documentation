## [Description](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#description)

The Volume Oscillator uses the difference between two [moving averages](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma) of [volume](https://developer.ninjatrader.com/docs/desktop/volume) to determine if the trend is increasing or decreasing. A value above zero indicates that the shorter term volume moving average has risen above the longer term volume moving average. This indicates that the shorter term trend is higher than the longer term trend. Rising prices with with increased short term volume is bullish as is falling prices with decreased volume. Falling prices with increased volume or rising prices with decreased volume indicate market weakness.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#syntax)

`VolumeOscillator(int fast, int slow)`

`VolumeOscillator(ISeries<double> input, int fast, int slow)`

**Returns default value**

`VolumeOscillator(int fast, int slow)[int barsAgo]`

`VolumeOscillator(ISeries<double> input, int fast, int slow) [int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| fast | The number of bars to include in the short term moving average |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| slow | The number of bars to include in the long term moving average |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#example)

```jsx-150469391 csharp
// Prints the current value of a Volume Oscillator
double value = VolumeOscillator(12, 26)[0];
Print("The current Volume Oscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#description)

The Volume Oscillator uses the difference between two [moving averages](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma) of [volume](https://developer.ninjatrader.com/docs/desktop/volume) to determine if the trend is increasing or decreasing. A value above zero indicates that the shorter term volume moving average has risen above the longer term volume moving average. This indicates that the shorter term trend is higher than the longer term trend. Rising prices with with increased short term volume is bullish as is falling prices with decreased volume. Falling prices with increased volume or rising prices with decreased volume indicate market weakness.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#syntax)

`VolumeOscillator(int fast, int slow)`

`VolumeOscillator(ISeries<double> input, int fast, int slow)`

**Returns default value**

`VolumeOscillator(int fast, int slow)[int barsAgo]`

`VolumeOscillator(ISeries<double> input, int fast, int slow) [int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| fast | The number of bars to include in the short term moving average |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| slow | The number of bars to include in the long term moving average |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#example)

```jsx-150469391 csharp
// Prints the current value of a Volume Oscillator
double value = VolumeOscillator(12, 26)[0];
Print("The current Volume Oscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.