## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#description)

The Moving Average Ribbon is a series of incrementing moving averages.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#syntax)

`MovingAverageribbon(RibbonMAType movingAverage, int basePeriod, int incrementalPeriod)`

`MovingAverageribbon(ISeries<double> input, RibbonMAType movingAverage, int basePeriod, int incrementalPeriod)`

**Returns the MovingAverage1 value (Replace the 1 with the desired moving average you want the value to return)**

`MovingAverageribbon(RibbonMAType movingAverage, int basePeriod, int incrementalPeriod).MovingAverage1[int barsAgo]`

`MovingAverageribbon(ISeries<double> input, RibbonMAType movingAverage, int basePeriod, int incrementalPeriod).MovingAverage1[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#parameters)

| input | RibbonMAType | basePeriod | incrementalPeriod |
| --- | --- | --- | --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | Moving average to use for calculations | Number of bars used in the calculation for the fastest moving average | Number of bars to increase for the calculation in each additional moving average |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#examples)

```jsx-150469391 csharp
// Prints the current value of the 3rd moving average
double value = MovingAverageRibbon(RibbonMAType.Exponential, 10, 10).MovingAverage3[0];
Print("The current 3rd moving average's value is " + value.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#description)

The Moving Average Ribbon is a series of incrementing moving averages.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#syntax)

`MovingAverageribbon(RibbonMAType movingAverage, int basePeriod, int incrementalPeriod)`

`MovingAverageribbon(ISeries<double> input, RibbonMAType movingAverage, int basePeriod, int incrementalPeriod)`

**Returns the MovingAverage1 value (Replace the 1 with the desired moving average you want the value to return)**

`MovingAverageribbon(RibbonMAType movingAverage, int basePeriod, int incrementalPeriod).MovingAverage1[int barsAgo]`

`MovingAverageribbon(ISeries<double> input, RibbonMAType movingAverage, int basePeriod, int incrementalPeriod).MovingAverage1[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#parameters)

| input | RibbonMAType | basePeriod | incrementalPeriod |
| --- | --- | --- | --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | Moving average to use for calculations | Number of bars used in the calculation for the fastest moving average | Number of bars to increase for the calculation in each additional moving average |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_ribbon\#examples)

```jsx-150469391 csharp
// Prints the current value of the 3rd moving average
double value = MovingAverageRibbon(RibbonMAType.Exponential, 10, 10).MovingAverage3[0];
Print("The current 3rd moving average's value is " + value.ToString());

```