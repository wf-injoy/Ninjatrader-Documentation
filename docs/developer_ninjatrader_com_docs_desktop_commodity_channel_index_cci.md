## [Description](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#description)

Developed by Donald Lambert, the Commodity Channel Index (CCI) was designed to identify cyclical turns in commodities. The assumption behind the indicator is that commodities (or stocks or bonds) move in cycles, with highs and lows coming at periodic intervals.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_CCI.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#syntax)

`CCI(int period)`

`CCI(ISeries<double> input, int period)`

**Returns default value**

`CCI(int period)[int barsAgo]`

`CCI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#examples)

```jsx-150469391 csharp

// Prints the current value of a 20 period CCI using default price type
double value = CCI(20)[0];
Print("The current CCI value is " + value.ToString());

// Prints the current value of a 20 period CCI using high price type
double value = CCI(High, 20)[0];
Print("The current CCI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#description)

Developed by Donald Lambert, the Commodity Channel Index (CCI) was designed to identify cyclical turns in commodities. The assumption behind the indicator is that commodities (or stocks or bonds) move in cycles, with highs and lows coming at periodic intervals.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_CCI.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#syntax)

`CCI(int period)`

`CCI(ISeries<double> input, int period)`

**Returns default value**

`CCI(int period)[int barsAgo]`

`CCI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#examples)

```jsx-150469391 csharp

// Prints the current value of a 20 period CCI using default price type
double value = CCI(20)[0];
Print("The current CCI value is " + value.ToString());

// Prints the current value of a 20 period CCI using high price type
double value = CCI(High, 20)[0];
Print("The current CCI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/commodity_channel_index_cci\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.