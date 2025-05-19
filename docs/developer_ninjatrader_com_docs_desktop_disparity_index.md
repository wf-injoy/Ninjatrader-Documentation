## [Description](https://developer.ninjatrader.com/docs/desktop/disparity_index\#description)

The Disparity Index that measures the difference between the price and an exponential moving average. A value greater could suggest bullish momentum, while a value less than zero could suggest bearish momentum.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/disparity_index\#syntax)

`DisparityIndex(int period)`

`DisparityIndex(ISeries<double> input, int period)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/disparity_index\#return-value)

**double;** Accessing this method via an index value **int barsAgo** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/disparity_index\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/disparity_index\#examples)

```jsx-150469391 csharp
// Prints the current value of a 15 period Disparity Index
double value = DisparityIndex(15)[0];
Print("The current Disparity Index value is " + value.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/disparity_index\#description)

The Disparity Index that measures the difference between the price and an exponential moving average. A value greater could suggest bullish momentum, while a value less than zero could suggest bearish momentum.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/disparity_index\#syntax)

`DisparityIndex(int period)`

`DisparityIndex(ISeries<double> input, int period)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/disparity_index\#return-value)

**double;** Accessing this method via an index value **int barsAgo** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/disparity_index\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/disparity_index\#examples)

```jsx-150469391 csharp
// Prints the current value of a 15 period Disparity Index
double value = DisparityIndex(15)[0];
Print("The current Disparity Index value is " + value.ToString());

```