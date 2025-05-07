## [Description](https://developer.ninjatrader.com/docs/desktop/trend-lines\#description)

When a high swing is followed by a lower high swing, a trend line high is automatically plotted. When a low swing is followed by a higher low swing, a trend line low is automatically plotted.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/trend-lines\#syntax)

`TrendLines(int strength, int numberOfTrendLines, int oldTrendsOpacity, bool alertOnBreak)`

`TrendLines(ISeries<double> input, int strength, int numberOfTrendLines, int oldTrendsOpacity, bool alertOnBreak)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/trend-lines\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/trend-lines\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| strength | The number of required bars to the left and right of the swing point |
| numberOfTrendLines | The number of recent trend lines to plot |
| oldTrendOpacity | The opacity to apply to old trend lines |
| alertOnBreak | Sets if there should be an alert when the price breaks the current trend line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/trend-lines\#examples)

```jsx-150469391 csharp
// Prints the current value of a 5 strength Trend Lines
double value = TrendLines(5, 4, 25, true)[0];
Print("The current Trend Lines value is " + value.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/trend-lines\#description)

When a high swing is followed by a lower high swing, a trend line high is automatically plotted. When a low swing is followed by a higher low swing, a trend line low is automatically plotted.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/trend-lines\#syntax)

`TrendLines(int strength, int numberOfTrendLines, int oldTrendsOpacity, bool alertOnBreak)`

`TrendLines(ISeries<double> input, int strength, int numberOfTrendLines, int oldTrendsOpacity, bool alertOnBreak)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/trend-lines\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/trend-lines\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| strength | The number of required bars to the left and right of the swing point |
| numberOfTrendLines | The number of recent trend lines to plot |
| oldTrendOpacity | The opacity to apply to old trend lines |
| alertOnBreak | Sets if there should be an alert when the price breaks the current trend line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/trend-lines\#examples)

```jsx-150469391 csharp
// Prints the current value of a 5 strength Trend Lines
double value = TrendLines(5, 4, 25, true)[0];
Print("The current Trend Lines value is " + value.ToString());

```