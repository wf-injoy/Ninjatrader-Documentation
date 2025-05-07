## [Description](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#description)

Developed by Ian Copsey, **Relative Spread Strength** is a variation to the [Relative Strength Index](https://developer.ninjatrader.com/docs/desktop/relative_strength_index_rsi).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#syntax)

`RSS(int eMA1, int eMA2, int length)`

`RSS(ISeries<double> input, int eMA1, int eMA2, int length)`

**Returns default value**

`RSS(int eMA1, int eMA2, int length)[int barsAgo]`

`RSS(ISeries<double> input, int eMA1, int eMA2, int length)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#parameters)

| Parameter | Description |
| --- | --- |
| eMA1 | First EMA's period |
| eMA2 | Second EMA's period |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| length | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#examples)

```jsx-150469391 csharp
// Prints the current value of the RSS using default price type
double value = RSS(10, 40, 5)[0];
Print("The current RSS value is " + value.ToString());

// Prints the current value of the RSS using high price type
double value = RSS(High, 10, 40, 5)[0];
Print("The current RSS value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#description)

Developed by Ian Copsey, **Relative Spread Strength** is a variation to the [Relative Strength Index](https://developer.ninjatrader.com/docs/desktop/relative_strength_index_rsi).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#syntax)

`RSS(int eMA1, int eMA2, int length)`

`RSS(ISeries<double> input, int eMA1, int eMA2, int length)`

**Returns default value**

`RSS(int eMA1, int eMA2, int length)[int barsAgo]`

`RSS(ISeries<double> input, int eMA1, int eMA2, int length)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#parameters)

| Parameter | Description |
| --- | --- |
| eMA1 | First EMA's period |
| eMA2 | Second EMA's period |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| length | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#examples)

```jsx-150469391 csharp
// Prints the current value of the RSS using default price type
double value = RSS(10, 40, 5)[0];
Print("The current RSS value is " + value.ToString());

// Prints the current value of the RSS using high price type
double value = RSS(High, 10, 40, 5)[0];
Print("The current RSS value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/relative_spread_strength_rss\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.