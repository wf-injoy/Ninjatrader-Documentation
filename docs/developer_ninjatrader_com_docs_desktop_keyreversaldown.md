## [Description](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#description)

Returns a value of 1 when the current close is less than the prior close and the current high has penetrated the highest high of the last n bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#syntax)

`KeyReversalDown(int period)`

`KeyReversalDown(ISeries<double> input, int period)`

**Returns default value**

`KeyReversalDown(int period)[int barsAgo]`

`KeyReversalDown(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#examples)

```jsx-150469391 csharp
// If we get a reversal over the past 10 bars go short
if (KeyReversalDown(10)[0] == 1)
    EnterShort();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#description)

Returns a value of 1 when the current close is less than the prior close and the current high has penetrated the highest high of the last n bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#syntax)

`KeyReversalDown(int period)`

`KeyReversalDown(ISeries<double> input, int period)`

**Returns default value**

`KeyReversalDown(int period)[int barsAgo]`

`KeyReversalDown(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#examples)

```jsx-150469391 csharp
// If we get a reversal over the past 10 bars go short
if (KeyReversalDown(10)[0] == 1)
    EnterShort();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/keyreversaldown\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.