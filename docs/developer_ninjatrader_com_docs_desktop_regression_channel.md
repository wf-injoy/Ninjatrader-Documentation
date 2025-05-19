## [Description](https://developer.ninjatrader.com/docs/desktop/regression_channel\#description)

A Regression Channel is created by drawing parallel lines above and below the **Linear Regression** line.

Parallel and equidistant lines are drawn n standard deviations (width parameter) above and below a Linear Regression trendline. The distance between the channel lines and the regression line is the greatest distance that any one closing price is from the regression line. Regression Channels contain price movement, the top channel line provides resistance and the bottom channel line provides support. A reversal in trend may be indicated when prices remain outside the channel for a longer period of time.

A Linear Regression trendline shows where equilibrium exists but Linear Regression Channels show the range prices can be expected to deviate from a trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/regression_channel\#syntax)

`RegressionChannel(int period, double width)`

`RegressionChannel(ISeries<double> input, int period, double width)`

**Returns default midline value**

`RegressionChannel(int period, double width)[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width)[int barsAgo]`

**Returns upper channel value**

`RegressionChannel(int period, double width).Upper[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width).Upper[int barsAgo]`

**Returns lower channel value**

`RegressionChannel(int period, double width).Lower[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/regression_channel\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/regression_channel\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| width | Number of std deviations to calculate the channel lines |

## Note

Tip: You should not access historical values of this indicator since the values can change from bar to bar. The values from n bars ago does not reflect what the values of the current bar really are. It is suggested that you only access the current bar value for this indicator.

## [Examples](https://developer.ninjatrader.com/docs/desktop/regression_channel\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period channel using default price type
double value = RegressionChannel(20, 2).Upper[0];
Print("The current upper channel value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/regression_channel\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/regression_channel\#description)

A Regression Channel is created by drawing parallel lines above and below the **Linear Regression** line.

Parallel and equidistant lines are drawn n standard deviations (width parameter) above and below a Linear Regression trendline. The distance between the channel lines and the regression line is the greatest distance that any one closing price is from the regression line. Regression Channels contain price movement, the top channel line provides resistance and the bottom channel line provides support. A reversal in trend may be indicated when prices remain outside the channel for a longer period of time.

A Linear Regression trendline shows where equilibrium exists but Linear Regression Channels show the range prices can be expected to deviate from a trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/regression_channel\#syntax)

`RegressionChannel(int period, double width)`

`RegressionChannel(ISeries<double> input, int period, double width)`

**Returns default midline value**

`RegressionChannel(int period, double width)[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width)[int barsAgo]`

**Returns upper channel value**

`RegressionChannel(int period, double width).Upper[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width).Upper[int barsAgo]`

**Returns lower channel value**

`RegressionChannel(int period, double width).Lower[int barsAgo]`

`RegressionChannel(ISeries<double> input, int period, double width).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/regression_channel\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/regression_channel\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| width | Number of std deviations to calculate the channel lines |

## Note

Tip: You should not access historical values of this indicator since the values can change from bar to bar. The values from n bars ago does not reflect what the values of the current bar really are. It is suggested that you only access the current bar value for this indicator.

## [Examples](https://developer.ninjatrader.com/docs/desktop/regression_channel\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period channel using default price type
double value = RegressionChannel(20, 2).Upper[0];
Print("The current upper channel value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/regression_channel\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.