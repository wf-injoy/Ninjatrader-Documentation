## [Description](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#description)

An indicator used in technical analysis as an objective value for the strength of trend. ADX is non-directional so it will quantify a trend's strength regardless of whether it is up or down. ADX is usually plotted in a chart window along with two lines known as the DMI (Directional Movement Indicators). ADX is derived from the relationship of the DMI lines.

... Courtesy of [Investopedia](http://investopedia.com/terms/a/adx.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#syntax)

`ADX(int period)`

`ADX(ISeries<` double `> input, int period)`

**Returns default value**

`ADX(int period)[int barsAgo]`

`ADX(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ADX
double value = ADX(20)[0];
Print("The current ADX value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#description)

An indicator used in technical analysis as an objective value for the strength of trend. ADX is non-directional so it will quantify a trend's strength regardless of whether it is up or down. ADX is usually plotted in a chart window along with two lines known as the DMI (Directional Movement Indicators). ADX is derived from the relationship of the DMI lines.

... Courtesy of [Investopedia](http://investopedia.com/terms/a/adx.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#syntax)

`ADX(int period)`

`ADX(ISeries<` double `> input, int period)`

**Returns default value**

`ADX(int period)[int barsAgo]`

`ADX(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ADX
double value = ADX(20)[0];
Print("The current ADX value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.