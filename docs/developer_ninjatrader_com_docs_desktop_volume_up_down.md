## [Description](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#description)

Variation of the [VOL](https://developer.ninjatrader.com/docs/desktop/volume) (Volume) indicator that colors the volume histogram different color depending if the current bar is up or down bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#syntax)

`VolumeUpDown()`

`VolumeUpDown(ISeries<double> input)`

**Returns default value**

`VolumeUpDown()[int barsAgo]`

`VolumeUpDown(ISeries<double> input](int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#example)

```jsx-150469391 csharp
// Prints the current value VolumeUpDown
double value = VolumeUpDown()[0];
Print("The current Volume value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#description)

Variation of the [VOL](https://developer.ninjatrader.com/docs/desktop/volume) (Volume) indicator that colors the volume histogram different color depending if the current bar is up or down bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#syntax)

`VolumeUpDown()`

`VolumeUpDown(ISeries<double> input)`

**Returns default value**

`VolumeUpDown()[int barsAgo]`

`VolumeUpDown(ISeries<double> input](int barsAgo)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#example)

```jsx-150469391 csharp
// Prints the current value VolumeUpDown
double value = VolumeUpDown()[0];
Print("The current Volume value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume_up_down\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.