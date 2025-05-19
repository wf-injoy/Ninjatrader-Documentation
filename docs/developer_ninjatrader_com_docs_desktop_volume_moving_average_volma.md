## [Description](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#description)

The Volume Moving Average indicator is an indicator on indicator implementation. It calculates and returns the value of an [exponential moving average](https://developer.ninjatrader.com/docs/desktop/moving_average_exponential_ema) of [volume](https://developer.ninjatrader.com/docs/desktop/volume).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#syntax)

`VOLMA(int period)`

`VOLMA(ISeries<double> input, int period)`

**Returns default value**

`VOLMA[int period] (int barsAgo)`

`VOLMA[ISeries<` double `> input, int period] (int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#example)

```jsx-150469391 csharp
// Evaluates if the current volume is greater than the 20 period EMA of volume
if (Volume[0] > VOLMA(20)[0])
  Print("Volume has risen above its 20 period average");

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#description)

The Volume Moving Average indicator is an indicator on indicator implementation. It calculates and returns the value of an [exponential moving average](https://developer.ninjatrader.com/docs/desktop/moving_average_exponential_ema) of [volume](https://developer.ninjatrader.com/docs/desktop/volume).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#syntax)

`VOLMA(int period)`

`VOLMA(ISeries<double> input, int period)`

**Returns default value**

`VOLMA[int period] (int barsAgo)`

`VOLMA[ISeries<` double `> input, int period] (int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#example)

```jsx-150469391 csharp
// Evaluates if the current volume is greater than the 20 period EMA of volume
if (Volume[0] > VOLMA(20)[0])
  Print("Volume has risen above its 20 period average");

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_moving_average_volma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.