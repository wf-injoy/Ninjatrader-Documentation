## [Description](https://developer.ninjatrader.com/docs/desktop/vortex\#description)

The Vortex indicator is an oscillator used to identify trends. A bullish signal triggers when the VIPlus line crosses above the VIMinus line. A bearish signal triggers when the VIMinus line crosses above the VIPlus line.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/vortex\#syntax)

`Vortex(int period)`

`Vortex(ISeries<double> input, int period)`

**Returns VIPlus value**

`Vortex(int period).VIPlus[int barsAgo]`

`Vortex(ISeries<` double `> input, int period).VIPlus[int barsAgo]`

**Returns VIMinus value**

`Vortex(int period).VIMinus[int barsAgo]`

`Vortex(ISeries<double> input, int period).VIMinus[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/vortex\#return-value)

- **double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/vortex\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/vortex\#examples)

```jsx-150469391 csharp
// Prints the current VIPlus value of a 14 period Vortex
double valueP = Vortex(14).VIPlus[0];
Print("The current Vortex VIPlus value is " + valueP.ToString());

// Prints the current VIMinus value of a 14 period Vortex
double valueM = Vortex(14).VIMinus[0];
Print("The current Vortex VIMinusvalue is " + valueM.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/vortex\#description)

The Vortex indicator is an oscillator used to identify trends. A bullish signal triggers when the VIPlus line crosses above the VIMinus line. A bearish signal triggers when the VIMinus line crosses above the VIPlus line.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/vortex\#syntax)

`Vortex(int period)`

`Vortex(ISeries<double> input, int period)`

**Returns VIPlus value**

`Vortex(int period).VIPlus[int barsAgo]`

`Vortex(ISeries<` double `> input, int period).VIPlus[int barsAgo]`

**Returns VIMinus value**

`Vortex(int period).VIMinus[int barsAgo]`

`Vortex(ISeries<double> input, int period).VIMinus[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/vortex\#return-value)

- **double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/vortex\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/vortex\#examples)

```jsx-150469391 csharp
// Prints the current VIPlus value of a 14 period Vortex
double valueP = Vortex(14).VIPlus[0];
Print("The current Vortex VIPlus value is " + valueP.ToString());

// Prints the current VIMinus value of a 14 period Vortex
double valueM = Vortex(14).VIMinus[0];
Print("The current Vortex VIMinusvalue is " + valueM.ToString());

```