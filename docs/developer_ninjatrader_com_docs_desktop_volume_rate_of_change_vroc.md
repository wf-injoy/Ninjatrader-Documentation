## [Description](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#description)

Volume Rate of Change is identical to [Price Rate Of Change (ROC)](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc) indicator except that it uses volume instead of price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#syntax)

`VROC(int period, int smooth)`

`VROC(ISeries<double> input, int period, int smooth)`

**Returns default value**

`VROC(int period, int smooth)[int barsAgo]`

`VROC(ISeries<double> input, int period, int smooth] (int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| smooth | The number of bars for smoothing the signal |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#example)

```jsx-150469391 csharp
// Prints the current value of VROC
double value = VROC(13, 3)[0];
Print("The current VROC value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#description)

Volume Rate of Change is identical to [Price Rate Of Change (ROC)](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc) indicator except that it uses volume instead of price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#syntax)

`VROC(int period, int smooth)`

`VROC(ISeries<double> input, int period, int smooth)`

**Returns default value**

`VROC(int period, int smooth)[int barsAgo]`

`VROC(ISeries<double> input, int period, int smooth] (int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| smooth | The number of bars for smoothing the signal |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#example)

```jsx-150469391 csharp
// Prints the current value of VROC
double value = VROC(13, 3)[0];
Print("The current VROC value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_rate_of_change_vroc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.