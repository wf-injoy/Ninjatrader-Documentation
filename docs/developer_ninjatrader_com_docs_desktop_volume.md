## [Description](https://developer.ninjatrader.com/docs/desktop/volume\#description)

Volume is simply the number of shares (or contracts) traded during a specified time frame (e.g., hour, day, week, month, etc). The analysis of volume is a basic yet very important element of technical analysis. Volume provides clues as to the intensity of a given price move.

... Courtesy of [Market In Out](http://www.marketinout.com/technical_analysis.php?id=114)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume\#syntax)

`VOL()`

`VOL(ISeries<double> input)`

**Returns default value**

`VOL()[int barsAgo]`

`VOL(ISeries<` double `> input)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [ISeriesT](https://developer.ninjatrader.com/docs/desktop/iseriest) |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume\#example)

```jsx-150469391 csharp
// Prints the current value VOL
double value = VOL()[0];
Print("The current VOL value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/volume\#description)

Volume is simply the number of shares (or contracts) traded during a specified time frame (e.g., hour, day, week, month, etc). The analysis of volume is a basic yet very important element of technical analysis. Volume provides clues as to the intensity of a given price move.

... Courtesy of [Market In Out](http://www.marketinout.com/technical_analysis.php?id=114)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/volume\#syntax)

`VOL()`

`VOL(ISeries<double> input)`

**Returns default value**

`VOL()[int barsAgo]`

`VOL(ISeries<` double `> input)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/volume\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/volume\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [ISeriesT](https://developer.ninjatrader.com/docs/desktop/iseriest) |

## [Example](https://developer.ninjatrader.com/docs/desktop/volume\#example)

```jsx-150469391 csharp
// Prints the current value VOL
double value = VOL()[0];
Print("The current VOL value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/volume\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.