## [Description](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#description)

Detects the specified candle stick pattern.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#syntax)

`CandleStickPattern(ChartPattern pattern, int trendStrength)`

`CandleStickPattern(ISeries<double> input, ChartPattern pattern, int trendStrength)`

**Returns a value indicating if the specified pattern was detected**

`CandleStickPattern(ChartPattern pattern, int trendStrength)[int barsAgo]`

`CandleStickPattern(ISeries<double> input, ChartPattern pattern, int trendStrength)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#return-value)

A **double** value representing pattern found. Returns a value of 1 if the pattern is found; returns a value of 0 if no pattern was found.

Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| pattern | Possible values are:<br>- **ChartPattern.BearishBeltHold**<br>- **ChartPattern.BearishEngulfing**<br>- **ChartPattern.BearishHarami**<br>- **ChartPattern.BearishHaramiCross**<br>- **ChartPattern.BullishBeltHold**<br>- **ChartPattern.BullishEngulfing**<br>- **ChartPattern.BullishHarami**<br>- **ChartPattern.BullishHaramiCross**<br>- **ChartPattern.DarkCloudCover**<br>- **ChartPattern.Doji**<br>- **ChartPattern.DownsideTasukiGap**<br>- **ChartPattern.EveningStar**<br>- **ChartPattern.FallingThreeMethods**<br>- **ChartPattern.Hammer**<br>- **ChartPattern.HangingMan**<br>- **ChartPattern.InvertedHammer**<br>- **ChartPattern.MorningStart**<br>- **ChartPattern.PiercingLine**<br>- **ChartPattern.RisingThreeMethods**<br>- **ChartPattern.ShootingStar**<br>- **ChartPattern.StickSandwich**<br>- **ChartPattern.ThreeBlackCrows**<br>- **ChartPattern.ThreeWhiteSoldiers**<br>- **ChartPattern.UpsideGapTwoCrows**<br>- **ChartPattern.UpsideTasukiGap** |
| trendStrength | The number of required bars to the left and right of the swing point used to determine trend. A value of zero will exclude the requirement of a trend and only detect based on the candles themselves. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#examples)

```jsx-150469391 csharp
// Go long if the current bar is a bullish engulfing pattern
if (CandleStickPattern(ChartPattern.BullishEngulfing, 4)[0] == 1)
    EnterLong();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#description)

Detects the specified candle stick pattern.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#syntax)

`CandleStickPattern(ChartPattern pattern, int trendStrength)`

`CandleStickPattern(ISeries<double> input, ChartPattern pattern, int trendStrength)`

**Returns a value indicating if the specified pattern was detected**

`CandleStickPattern(ChartPattern pattern, int trendStrength)[int barsAgo]`

`CandleStickPattern(ISeries<double> input, ChartPattern pattern, int trendStrength)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#return-value)

A **double** value representing pattern found. Returns a value of 1 if the pattern is found; returns a value of 0 if no pattern was found.

Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| pattern | Possible values are:<br>- **ChartPattern.BearishBeltHold**<br>- **ChartPattern.BearishEngulfing**<br>- **ChartPattern.BearishHarami**<br>- **ChartPattern.BearishHaramiCross**<br>- **ChartPattern.BullishBeltHold**<br>- **ChartPattern.BullishEngulfing**<br>- **ChartPattern.BullishHarami**<br>- **ChartPattern.BullishHaramiCross**<br>- **ChartPattern.DarkCloudCover**<br>- **ChartPattern.Doji**<br>- **ChartPattern.DownsideTasukiGap**<br>- **ChartPattern.EveningStar**<br>- **ChartPattern.FallingThreeMethods**<br>- **ChartPattern.Hammer**<br>- **ChartPattern.HangingMan**<br>- **ChartPattern.InvertedHammer**<br>- **ChartPattern.MorningStart**<br>- **ChartPattern.PiercingLine**<br>- **ChartPattern.RisingThreeMethods**<br>- **ChartPattern.ShootingStar**<br>- **ChartPattern.StickSandwich**<br>- **ChartPattern.ThreeBlackCrows**<br>- **ChartPattern.ThreeWhiteSoldiers**<br>- **ChartPattern.UpsideGapTwoCrows**<br>- **ChartPattern.UpsideTasukiGap** |
| trendStrength | The number of required bars to the left and right of the swing point used to determine trend. A value of zero will exclude the requirement of a trend and only detect based on the candles themselves. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#examples)

```jsx-150469391 csharp
// Go long if the current bar is a bullish engulfing pattern
if (CandleStickPattern(ChartPattern.BullishEngulfing, 4)[0] == 1)
    EnterLong();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/candlestickpattern\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.