## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#description)

The Zero-Lag Exponential Moving Average is a variation on the Exponential Moving Average. The Zero-Lag keeps the benefit of the heavier weighting of recent values, but attempts to remove lag by subtracting older data to minimize the cumulative effect.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=ZeroLagExpMA.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#syntax)

`ZLEMA(int period)`

`ZLEMA(ISeries<double> input, int period)`

**Returns default value**

`ZLEMA(int period)[int barsAgo]`

`ZLEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ZLEMA using default price type
double value = ZLEMA(20)[0];
Print("The current SMA value is " + value.ToString());

// Prints the current value of a 20 period ZLEMA using high price type
double value = ZLEMA(High, 20)[0];
Print("The current ZLEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#description)

The Zero-Lag Exponential Moving Average is a variation on the Exponential Moving Average. The Zero-Lag keeps the benefit of the heavier weighting of recent values, but attempts to remove lag by subtracting older data to minimize the cumulative effect.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=ZeroLagExpMA.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#syntax)

`ZLEMA(int period)`

`ZLEMA(ISeries<double> input, int period)`

**Returns default value**

`ZLEMA(int period)[int barsAgo]`

`ZLEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ZLEMA using default price type
double value = ZLEMA(20)[0];
Print("The current SMA value is " + value.ToString());

// Prints the current value of a 20 period ZLEMA using high price type
double value = ZLEMA(High, 20)[0];
Print("The current ZLEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_zero_lag_exponential_zlema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.