## [Description](https://developer.ninjatrader.com/docs/desktop/williams_r\#description)

Developed by Larry Williams, Williams %R is a momentum indicator that works much like the [Stochastic Oscillator](https://developer.ninjatrader.com/docs/desktop/stochastics). It is especially popular for measuring overbought and oversold levels. The scale ranges from 0 to -100 with readings from 0 to -20 considered overbought, and readings from -80 to -100 considered oversold.

... Courtesy of [StockCharts](https://school.stockcharts.com/doku.php?id=technical_indicators:williams_r)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/williams_r\#syntax)

`WilliamsR(int period)`

`WilliamsR(ISeries<` double `> input, int period)`

**Returns default value**

`WilliamsR(int period)[int barsAgo]`

`WilliamsR(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/williams_r\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/williams_r\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/williams_r\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period WilliamsR using default price type
double value = WilliamsR(20)[0];
Print("The current WilliamsR value is " + value.ToString());

// Prints the current value of a 20 period WilliamsR using high price type
double value = WilliamsR(High, 20)[0];
Print("The current WilliamsR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/williams_r\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/williams_r\#description)

Developed by Larry Williams, Williams %R is a momentum indicator that works much like the [Stochastic Oscillator](https://developer.ninjatrader.com/docs/desktop/stochastics). It is especially popular for measuring overbought and oversold levels. The scale ranges from 0 to -100 with readings from 0 to -20 considered overbought, and readings from -80 to -100 considered oversold.

... Courtesy of [StockCharts](https://school.stockcharts.com/doku.php?id=technical_indicators:williams_r)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/williams_r\#syntax)

`WilliamsR(int period)`

`WilliamsR(ISeries<` double `> input, int period)`

**Returns default value**

`WilliamsR(int period)[int barsAgo]`

`WilliamsR(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/williams_r\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/williams_r\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/williams_r\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period WilliamsR using default price type
double value = WilliamsR(20)[0];
Print("The current WilliamsR value is " + value.ToString());

// Prints the current value of a 20 period WilliamsR using high price type
double value = WilliamsR(High, 20)[0];
Print("The current WilliamsR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/williams_r\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.