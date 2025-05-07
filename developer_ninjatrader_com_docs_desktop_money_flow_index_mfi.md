## [Description](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#description)

The Money Flow Index (MFI) is a momentum indicator that is similar to the Relative Strength Index (RSI) in both interpretation and calculation. However, MFI is a more rigid indicator in that it is volume-weighted, and is therefore a good measure of the strength of money flowing in and out of a security.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_MFI.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#syntax)

`MFI(int period)`

`MFI(ISeries<double> input, int period)`

**Returns default value**

`MFI(int period)[int barsAgo]`

`MFI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period MFI using default price type
double value = MFI(20)[0];
Print("The current MFI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#description)

The Money Flow Index (MFI) is a momentum indicator that is similar to the Relative Strength Index (RSI) in both interpretation and calculation. However, MFI is a more rigid indicator in that it is volume-weighted, and is therefore a good measure of the strength of money flowing in and out of a security.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_MFI.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#syntax)

`MFI(int period)`

`MFI(ISeries<double> input, int period)`

**Returns default value**

`MFI(int period)[int barsAgo]`

`MFI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period MFI using default price type
double value = MFI(20)[0];
Print("The current MFI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/money_flow_index_mfi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.