## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#description)

The HMA manages to keep up with rapid changes in price activity whilst having superior smoothing over an SMA of the same period. The HMA employs weighted moving averages and dampens the smoothing effect (and resulting lag) by using the square root of the period instead of the actual period itself. Developed by Alan Hull.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#syntax)

`HMA(int period)`

`HMA(ISeries<double> input, int period)`

**Returns default value**

`HMA(int period)[int barsAgo]`

`HMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period HMA using default price type
double value = HMA(20)[0];
Print("The current HMA value is " + value.ToString());

// Prints the current value of a 20 period HMA using high price type
double value = HMA(High, 20)[0];
Print("The current HMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#description)

The HMA manages to keep up with rapid changes in price activity whilst having superior smoothing over an SMA of the same period. The HMA employs weighted moving averages and dampens the smoothing effect (and resulting lag) by using the square root of the period instead of the actual period itself. Developed by Alan Hull.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#syntax)

`HMA(int period)`

`HMA(ISeries<double> input, int period)`

**Returns default value**

`HMA(int period)[int barsAgo]`

`HMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period HMA using default price type
double value = HMA(20)[0];
Print("The current HMA value is " + value.ToString());

// Prints the current value of a 20 period HMA using high price type
double value = HMA(High, 20)[0];
Print("The current HMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_hull_hma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.