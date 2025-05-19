## [Description](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#description)

An indicator used in technical analysis that determines overbought and oversold conditions of a particular asset. This indicator is very similar to the relative strength index ( **RSI**). The main difference between the two is that the **RSI** uses a fixed number of time periods (usually 14), while the dynamic momentum index uses different time periods as volatility changes.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/dynamicmomentumindex.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#syntax)

`DMIndex(int smooth)`

`DMIndex(ISeries<double> input, int smooth)`

**Returns default value**

`DMIndex(int period)[barsAgo]`

`DMIndex(ISeries<double> input, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#return-value)

**double**; Accessing this method via an index value \[ **int barsAgo**\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#parameters)

| input | smooth |
| --- | --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | The number of bars to include in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#examples)

```jsx-150469391 csharp
// Prints the current value of DMIndex using default price type
double value = DMIndex(3)[0];
Print("The current DMIndex value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#description)

An indicator used in technical analysis that determines overbought and oversold conditions of a particular asset. This indicator is very similar to the relative strength index ( **RSI**). The main difference between the two is that the **RSI** uses a fixed number of time periods (usually 14), while the dynamic momentum index uses different time periods as volatility changes.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/dynamicmomentumindex.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#syntax)

`DMIndex(int smooth)`

`DMIndex(ISeries<double> input, int smooth)`

**Returns default value**

`DMIndex(int period)[barsAgo]`

`DMIndex(ISeries<double> input, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#return-value)

**double**; Accessing this method via an index value \[ **int barsAgo**\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#parameters)

| input | smooth |
| --- | --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) | The number of bars to include in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#examples)

```jsx-150469391 csharp
// Prints the current value of DMIndex using default price type
double value = DMIndex(3)[0];
Print("The current DMIndex value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/dynamic_momentum_index_dmindex\#source-code)

You can view this indicator method source code by selecting the menu New > **NinjaScript** Editor > Indicators within the **NinjaTrader** Control Center window.