## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#description)

The Simple Moving Average is calculated by summing the closing prices of the security for a period of time and then dividing this total by the number of time periods. Sometimes called an arithmetic moving average, the SMA is basically the average stock price over time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#syntax)

`SMA(int period)`

`SMA(ISeries<double> input, int period)`

\*\*Returns default value \*\*

`SMA(int period)[int barsAgo]`

`SMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period SMA using default price type
double value = SMA(20)[0];
Print("The current SMA value is " + value.ToString());

// Prints the current value of a 20 period SMA using high price type**
double value = SMA(High, 20)[0];
Print("The current SMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#description)

The Simple Moving Average is calculated by summing the closing prices of the security for a period of time and then dividing this total by the number of time periods. Sometimes called an arithmetic moving average, the SMA is basically the average stock price over time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#syntax)

`SMA(int period)`

`SMA(ISeries<double> input, int period)`

\*\*Returns default value \*\*

`SMA(int period)[int barsAgo]`

`SMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period SMA using default price type
double value = SMA(20)[0];
Print("The current SMA value is " + value.ToString());

// Prints the current value of a 20 period SMA using high price type**
double value = SMA(High, 20)[0];
Print("The current SMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_simple_sma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.