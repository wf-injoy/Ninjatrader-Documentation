## [Description](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#description)

Returns a value of 1 when the current close is greater than the prior close and the current low has penetrated the lowest low of the last n bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#syntax)

`KeyReversalUp(int period)`

`KeyReversalUp(ISeries<double> input, int period)`

**Returns default value**

`KeyReversalUp(int period)[int barsAgo]`

`KeyReversalUp(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#examples)

```jsx-150469391 csharp
// If we get a reversal over the past 10 bars go long
if (KeyReversalUp(10)[0] == 1)
    EnterLong();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#description)

Returns a value of 1 when the current close is greater than the prior close and the current low has penetrated the lowest low of the last n bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#syntax)

`KeyReversalUp(int period)`

`KeyReversalUp(ISeries<double> input, int period)`

**Returns default value**

`KeyReversalUp(int period)[int barsAgo]`

`KeyReversalUp(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#examples)

```jsx-150469391 csharp
// If we get a reversal over the past 10 bars go long
if (KeyReversalUp(10)[0] == 1)
    EnterLong();

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/keyreversalup\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.