## [Description](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#description)

In probability theory and statistics, **standard deviation** is a measure of the variability or dispersion of a population, a data set, or a probability distribution. A low **standard deviation** indicates that the data points tend to be very close to the same value (the mean), while high **standard deviation** indicates that the data are “spread out” over a large range of values.

... Courtesy of [Wikipedia](https://en.wikipedia.org/wiki/Standard_deviation)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#syntax)

`StdDev(int period)`

`StdDev(ISeries<double> input, int period)`

**Returns default value**

`StdDev(int period)[int barsAgo]`

`StdDev(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period **StdDev** using default price type
double value = StdDev(20)[0];
Print("The current **StdDev** value is " + value.ToString());

// Prints the current value of a 20 period **StdDev** using high price type
double value = StdDev(High, 20)[0];
Print("The current **StdDev** value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#description)

In probability theory and statistics, **standard deviation** is a measure of the variability or dispersion of a population, a data set, or a probability distribution. A low **standard deviation** indicates that the data points tend to be very close to the same value (the mean), while high **standard deviation** indicates that the data are “spread out” over a large range of values.

... Courtesy of [Wikipedia](https://en.wikipedia.org/wiki/Standard_deviation)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#syntax)

`StdDev(int period)`

`StdDev(ISeries<double> input, int period)`

**Returns default value**

`StdDev(int period)[int barsAgo]`

`StdDev(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period **StdDev** using default price type
double value = StdDev(20)[0];
Print("The current **StdDev** value is " + value.ToString());

// Prints the current value of a 20 period **StdDev** using high price type
double value = StdDev(High, 20)[0];
Print("The current **StdDev** value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/standard_deviation_stddev\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.