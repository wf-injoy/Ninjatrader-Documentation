## [Description](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#description)

Developed by John Bollinger, Bollinger Bands are an indicator that allows users to compare volatility and relative price levels over a period time. The indicator consists of three bands designed to encompass the majority of a security's price action.

1. A simple moving average in the middle
2. An upper band (SMA plus 2 standard deviations)
3. A lower band (SMA minus 2 standard deviations)

Standard deviation is a statistical unit of measure that provides a good assessment of a price plot's volatility. Using the standard deviation ensures that the bands will react quickly to price movements and reflect periods of high and low volatility. Sharp price increases (or decreases), and hence volatility, will lead to a widening of the bands.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_Bbands.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#syntax)

`Bollinger(double numStdDev, int period)`

`Bollinger(ISeries<` double `> input, double numStdDev, int period)`

**Returns upper band value** `Bollinger(double numStdDev, int period).Upper[int barsAgo]`

`Bollinger(ISeries<` double `> input, double numStdDev, int period).Upper[int barsAgo]`

**Returns lower band value**

`Bollinger(double numStdDev, int period).Lower[int barsAgo]`

`Bollinger(ISeries<double> input, double numStdDev, int period).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#examples)

```jsx-150469391 csharp
// Prints the current upper band value of a 20 period Bollinger using default price type
double upperValue = Bollinger(2, 20).Upper[0];
Print("The current Bollinger upper value is " + upperValue.ToString());

// Prints the current upper band value of a 20 period Bollinger using low price type
double upperValue = Bollinger(Low, 2, 20).Upper[0];
Print("The current Bollinger upper value is " + upperValue.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#description)

Developed by John Bollinger, Bollinger Bands are an indicator that allows users to compare volatility and relative price levels over a period time. The indicator consists of three bands designed to encompass the majority of a security's price action.

1. A simple moving average in the middle
2. An upper band (SMA plus 2 standard deviations)
3. A lower band (SMA minus 2 standard deviations)

Standard deviation is a statistical unit of measure that provides a good assessment of a price plot's volatility. Using the standard deviation ensures that the bands will react quickly to price movements and reflect periods of high and low volatility. Sharp price increases (or decreases), and hence volatility, will lead to a widening of the bands.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_Bbands.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#syntax)

`Bollinger(double numStdDev, int period)`

`Bollinger(ISeries<` double `> input, double numStdDev, int period)`

**Returns upper band value** `Bollinger(double numStdDev, int period).Upper[int barsAgo]`

`Bollinger(ISeries<` double `> input, double numStdDev, int period).Upper[int barsAgo]`

**Returns lower band value**

`Bollinger(double numStdDev, int period).Lower[int barsAgo]`

`Bollinger(ISeries<double> input, double numStdDev, int period).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#examples)

```jsx-150469391 csharp
// Prints the current upper band value of a 20 period Bollinger using default price type
double upperValue = Bollinger(2, 20).Upper[0];
Print("The current Bollinger upper value is " + upperValue.ToString());

// Prints the current upper band value of a 20 period Bollinger using low price type
double upperValue = Bollinger(Low, 2, 20).Upper[0];
Print("The current Bollinger upper value is " + upperValue.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/bollinger_bands\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.