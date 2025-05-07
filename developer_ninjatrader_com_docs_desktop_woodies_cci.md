## [Description](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#description)

NinjaTrader provides the **Woodies CCI** indicator. It's implemented as specified by Woodie.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#syntax)

`WoodiesCCI()`

`WoodiesCCI(ISeries<double> input)`

**Returns default value**

`WoodiesCCI()[int barsAgo]`

`WoodiesCCI(ISeries<double> input)[int barsAgo]`

**Returns turbo value**

`WoodiesCCI().Turbo[int barsAgo]`

`WoodiesCCI(ISeries<double> input).Turbo[int barsAgo]`

**Returns histogram bar color**

`WoodiesCCI().ZoneBars[int barsAgo]`

`WoodiesCCI(ISeries<` double `> input).ZoneBars[int barsAgo]`

Return values representing the chopzone plot color are as follows:

- 0 = Negative (default color is red)
- 1 = Positive (default color is blue)
- 2 = Neutral (default color is gray)
- 3 = Last neutral bar (default color is yellow)

**Returns chopzone value**

`WoodiesCCI().ChopZone[int barsAgo]`

`WoodiesCCI(ISeries<` double `> input).ChopZone[int barsAgo]`

Return values representing the chopzone plot color are as follows:

- -4 = DarkRed
- -3 = LightRed
- -2 = DarkOrange
- -1 = LightOrange
- 0 = Yellow
- 1 = Lime
- 2 = LightGreen
- 3 = DarkGreen
- 4 = Cyan

**Returns sidewinder value**

`WoodiesCCI().Sidewinder[int barsAgo]`

`WoodiesCCI(ISeries<double> input).Sidewinder[int barsAgo]`

Return values representing the sidewinder plot value are as follows:

- -1 = Warning
- 0 = Neutral
- 1 = Trending

## [Return Value](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Example](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#example)

```jsx-150469391 csharp
// Prints the current value of a 14 period WoodiesCCI using default price type
double value = WoodiesCCI(2, 5, 14, 34, 25, 6, 60, 100, 2)[0];
Print("The current WoodiesCCI value is " + value.ToString());

// Prints the current turbo value of a 14 / 6 period WoodiesCCI using default price type
double value2 = WoodiesCCI(2, 5, 14, 34, 25, 6, 60, 100, 2).Turbo[0];
Print("The current WoodiesCCI turbo value is " + value2.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#description)

NinjaTrader provides the **Woodies CCI** indicator. It's implemented as specified by Woodie.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#syntax)

`WoodiesCCI()`

`WoodiesCCI(ISeries<double> input)`

**Returns default value**

`WoodiesCCI()[int barsAgo]`

`WoodiesCCI(ISeries<double> input)[int barsAgo]`

**Returns turbo value**

`WoodiesCCI().Turbo[int barsAgo]`

`WoodiesCCI(ISeries<double> input).Turbo[int barsAgo]`

**Returns histogram bar color**

`WoodiesCCI().ZoneBars[int barsAgo]`

`WoodiesCCI(ISeries<` double `> input).ZoneBars[int barsAgo]`

Return values representing the chopzone plot color are as follows:

- 0 = Negative (default color is red)
- 1 = Positive (default color is blue)
- 2 = Neutral (default color is gray)
- 3 = Last neutral bar (default color is yellow)

**Returns chopzone value**

`WoodiesCCI().ChopZone[int barsAgo]`

`WoodiesCCI(ISeries<` double `> input).ChopZone[int barsAgo]`

Return values representing the chopzone plot color are as follows:

- -4 = DarkRed
- -3 = LightRed
- -2 = DarkOrange
- -1 = LightOrange
- 0 = Yellow
- 1 = Lime
- 2 = LightGreen
- 3 = DarkGreen
- 4 = Cyan

**Returns sidewinder value**

`WoodiesCCI().Sidewinder[int barsAgo]`

`WoodiesCCI(ISeries<double> input).Sidewinder[int barsAgo]`

Return values representing the sidewinder plot value are as follows:

- -1 = Warning
- 0 = Neutral
- 1 = Trending

## [Return Value](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Example](https://developer.ninjatrader.com/docs/desktop/woodies_cci\#example)

```jsx-150469391 csharp
// Prints the current value of a 14 period WoodiesCCI using default price type
double value = WoodiesCCI(2, 5, 14, 34, 25, 6, 60, 100, 2)[0];
Print("The current WoodiesCCI value is " + value.ToString());

// Prints the current turbo value of a 14 / 6 period WoodiesCCI using default price type
double value2 = WoodiesCCI(2, 5, 14, 34, 25, 6, 60, 100, 2).Turbo[0];
Print("The current WoodiesCCI turbo value is " + value2.ToString());

```