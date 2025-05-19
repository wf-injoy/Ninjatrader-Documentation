## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#description)

The Weighted Moving Average gives the latest price more weight than prior prices. Each prior price in the period gets progressively less weight as they become older.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#syntax)

`WMA(int period)`

`WMA(ISeries<double> input, int period)`

**Returns default value**

`WMA(int period)[int barsAgo]`

`WMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period WMA using default price type
double value = WMA(20)[0];
Print("The current WMA value is " + value.ToString());

// Prints the current value of a 20 period WMA using high price type
double value = WMA(High, 20)[0];
Print("The current WMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#description)

The Weighted Moving Average gives the latest price more weight than prior prices. Each prior price in the period gets progressively less weight as they become older.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#syntax)

`WMA(int period)`

`WMA(ISeries<double> input, int period)`

**Returns default value**

`WMA(int period)[int barsAgo]`

`WMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period WMA using default price type
double value = WMA(20)[0];
Print("The current WMA value is " + value.ToString());

// Prints the current value of a 20 period WMA using high price type
double value = WMA(High, 20)[0];
Print("The current WMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_weighted_wma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.