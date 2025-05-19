## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#description)

The Chaikin Volatility Indicator is the difference between two moving averages of a volume weighted accumulation-distribution line. By comparing the spread between a security's high and low prices, it quantifies volatility as a widening of the range between the high and the low price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#syntax)

`ChaikinVolatility(int mAPeriod, int rOCPeriod)`

`ChaikinVolatility(ISeries<double> input, int mAPeriod, int rOCPeriod)`

**Returns default value**

`ChaikinVolatility(int mAPeriod, int rOCPeriod)[int barsAgo]`

`ChaikinVolatility(ISeries<double> input, int mAPeriod, int rOCPeriod)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| mAPeriod | Number of bars used in the moving average calculation |
| rOCPeriod | Number of bars used in the rate of change calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#examples)

```jsx-150469391 csharp
// Prints the current value of the 20 period Chaikin Volatility
double value = ChaikinVolatility(20, 20)[0];
Print("The current Chaikin Volatility value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#description)

The Chaikin Volatility Indicator is the difference between two moving averages of a volume weighted accumulation-distribution line. By comparing the spread between a security's high and low prices, it quantifies volatility as a widening of the range between the high and the low price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#syntax)

`ChaikinVolatility(int mAPeriod, int rOCPeriod)`

`ChaikinVolatility(ISeries<double> input, int mAPeriod, int rOCPeriod)`

**Returns default value**

`ChaikinVolatility(int mAPeriod, int rOCPeriod)[int barsAgo]`

`ChaikinVolatility(ISeries<double> input, int mAPeriod, int rOCPeriod)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| mAPeriod | Number of bars used in the moving average calculation |
| rOCPeriod | Number of bars used in the rate of change calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#examples)

```jsx-150469391 csharp
// Prints the current value of the 20 period Chaikin Volatility
double value = ChaikinVolatility(20, 20)[0];
Print("The current Chaikin Volatility value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_volatility\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.