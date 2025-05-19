## [Description](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#description)

The Range indicator compares the intraday range (high - low) to the inter-day (close - previous close) range. When the inter-day range is less than the intraday range, the Range Indicator will be a high value. This signals an end to the current trend. When the Range Indicator is at a low level, a new trend is about to start.

The Range Indicator was developed by Jack Weinberg and was introduced in his article in the June, 1995 issue of Technical Analysis of Stocks & Commodities magazine.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#syntax)

`RIND(int periodQ, int smooth)`

```RIND(ISeries<double>`` input, int periodQ, int smooth)```

\*\*Returns default value \*\*

`RIND(int periodQ, int smooth)[int barsAgo]`

`RIND(ISeries<double> input, int periodQ, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| periodQ | The number of bars to include in the calculation for the short term stochastic range lookback |
| smooth | The number of bars to include for the EMA smoothing of the indicator |

## [Examples](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#examples)

```jsx-150469391 csharp
// Prints out a historical RIND value
double value = RIND(3, 10)[5];
Print("RIND value of 5 bars ago is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#description)

The Range indicator compares the intraday range (high - low) to the inter-day (close - previous close) range. When the inter-day range is less than the intraday range, the Range Indicator will be a high value. This signals an end to the current trend. When the Range Indicator is at a low level, a new trend is about to start.

The Range Indicator was developed by Jack Weinberg and was introduced in his article in the June, 1995 issue of Technical Analysis of Stocks & Commodities magazine.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#syntax)

`RIND(int periodQ, int smooth)`

```RIND(ISeries<double>`` input, int periodQ, int smooth)```

\*\*Returns default value \*\*

`RIND(int periodQ, int smooth)[int barsAgo]`

`RIND(ISeries<double> input, int periodQ, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| periodQ | The number of bars to include in the calculation for the short term stochastic range lookback |
| smooth | The number of bars to include for the EMA smoothing of the indicator |

## [Examples](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#examples)

```jsx-150469391 csharp
// Prints out a historical RIND value
double value = RIND(3, 10)[5];
Print("RIND value of 5 bars ago is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/range_indicator_rind\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.