## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#description)

The Double Exponential Moving Average (DEMA) is a combination of a single exponential moving average and a double exponential moving average. The advantage is that gives a reduced amount of lag time than either of the two separate moving averages alone.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#syntax)

`DEMA(int period)`

`DEMA(ISeries<double> input, int period)`

**Returns default value**

`DEMA(int period)[int barsAgo]`

`DEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period DEMA using default price type**
double value = DEMA(20)[0];
Print("The current DEMA value is " + value.ToString());
// Prints the current value of a 20 period DEMA using high price type**
double value = DEMA(High, 20)[0];
Print("The current DEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#description)

The Double Exponential Moving Average (DEMA) is a combination of a single exponential moving average and a double exponential moving average. The advantage is that gives a reduced amount of lag time than either of the two separate moving averages alone.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#syntax)

`DEMA(int period)`

`DEMA(ISeries<double> input, int period)`

**Returns default value**

`DEMA(int period)[int barsAgo]`

`DEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period DEMA using default price type**
double value = DEMA(20)[0];
Print("The current DEMA value is " + value.ToString());
// Prints the current value of a 20 period DEMA using high price type**
double value = DEMA(High, 20)[0];
Print("The current DEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_double_exponential_dema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.