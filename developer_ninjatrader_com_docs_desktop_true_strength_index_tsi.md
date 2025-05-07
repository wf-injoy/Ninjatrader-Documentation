## [Description](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#description)

The True Strength Index (TSI) is a momentum-based indicator, developed by William Blau. Designed to determine both trend and overbought/oversold conditions, the TSI is applicable to intraday time frames as well as long term trading.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#syntax)

`TSI(int fast, int slow)`

`TSI(ISeries<` double `> input, int fast, int slow)`

**Returns default value**

`TSI(int fast, int slow)[int barsAgo]`

`TSI(ISeries<` double `> input, int fast, int slow)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#parameters)

| Parameter | Description |
| --- | --- |
| fast | Period of the fast smoothing factor |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | Period of the slow smoothing factor |

## [Examples](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TSI using default price type
double value = TSI(20, 10)[0];
Print("The current TSI value is " + value.ToString());

// Prints the current value of a 20 period TSI using high price type
double value = TSI(High, 20, 10)[0];
Print("The current TSI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#description)

The True Strength Index (TSI) is a momentum-based indicator, developed by William Blau. Designed to determine both trend and overbought/oversold conditions, the TSI is applicable to intraday time frames as well as long term trading.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#syntax)

`TSI(int fast, int slow)`

`TSI(ISeries<` double `> input, int fast, int slow)`

**Returns default value**

`TSI(int fast, int slow)[int barsAgo]`

`TSI(ISeries<` double `> input, int fast, int slow)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#parameters)

| Parameter | Description |
| --- | --- |
| fast | Period of the fast smoothing factor |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | Period of the slow smoothing factor |

## [Examples](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TSI using default price type
double value = TSI(20, 10)[0];
Print("The current TSI value is " + value.ToString());

// Prints the current value of a 20 period TSI using high price type
double value = TSI(High, 20, 10)[0];
Print("The current TSI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/true_strength_index_tsi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.