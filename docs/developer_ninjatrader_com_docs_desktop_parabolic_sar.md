## [Description](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#description)

The parabolic SAR is a technical indicator that is used by many traders to determine the direction of an asset's momentum and the point in time when this momentum has a higher-than-normal probability of switching directions.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/02/042202.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#syntax)

`ParabolicSAR(double acceleration, double accelerationMax, double accelerationStep)`

`ParabolicSAR(ISeries<double> input, double acceleration, double accelerationMax, double accelerationStep)`

**Returns default value**

`ParabolicSAR(double acceleration, double accelerationMax, double accelerationStep)[int barsAgo]`

`ParabolicSAR(ISeries<double> input, double acceleration, double accelerationStep, double accelerationMax)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#parameters)

| **acceleration** | Acceleration value |
| **accelerationStep** | Step value used to increment acceleration value |
| **accelerationMax** | Max acceleration value |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#examples)

```jsx-150469391 csharp
// Prints the current value of ParabolicSAR using default price type
double value = ParabolicSAR(0.02, 0.2, 0.02)[0];
Print("The current ParabolicSAR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#description)

The parabolic SAR is a technical indicator that is used by many traders to determine the direction of an asset's momentum and the point in time when this momentum has a higher-than-normal probability of switching directions.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/02/042202.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#syntax)

`ParabolicSAR(double acceleration, double accelerationMax, double accelerationStep)`

`ParabolicSAR(ISeries<double> input, double acceleration, double accelerationMax, double accelerationStep)`

**Returns default value**

`ParabolicSAR(double acceleration, double accelerationMax, double accelerationStep)[int barsAgo]`

`ParabolicSAR(ISeries<double> input, double acceleration, double accelerationStep, double accelerationMax)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#parameters)

| **acceleration** | Acceleration value |
| **accelerationStep** | Step value used to increment acceleration value |
| **accelerationMax** | Max acceleration value |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#examples)

```jsx-150469391 csharp
// Prints the current value of ParabolicSAR using default price type
double value = ParabolicSAR(0.02, 0.2, 0.02)[0];
Print("The current ParabolicSAR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/parabolic_sar\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.