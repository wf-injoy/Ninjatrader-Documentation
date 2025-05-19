## [Description](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#description)

The Forecast Oscillator calculates the percentage difference between the actual price and the Time Series Forecast (the endpoint of a linear regression line). When the price and the forecast are equal, the Oscillator is zero. When the price is greater than the forecast, the Oscillator is greater than zero. When the price is less than the forecast, the Oscillator is less than zero.

... Courtesy of [FM Labs](http://www.fmlabs.com/reference/default.htm?url=ForecastOscillator.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#syntax)

`FOSC(int period)`

`FOSC(ISeries<double> input, int period)`

**Returns default value**

`FOSC(int period)[int barsAgo]`

`FOSC(ISeries<double> input, int period**)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#examples)

```jsx-150469391 csharp
// Evaluates if the current bar **FOSC** is above zero
if (FOSC(14)[0] > 0)
   Print("FOSC is above zero indicating prices may rise");

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#description)

The Forecast Oscillator calculates the percentage difference between the actual price and the Time Series Forecast (the endpoint of a linear regression line). When the price and the forecast are equal, the Oscillator is zero. When the price is greater than the forecast, the Oscillator is greater than zero. When the price is less than the forecast, the Oscillator is less than zero.

... Courtesy of [FM Labs](http://www.fmlabs.com/reference/default.htm?url=ForecastOscillator.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#syntax)

`FOSC(int period)`

`FOSC(ISeries<double> input, int period)`

**Returns default value**

`FOSC(int period)[int barsAgo]`

`FOSC(ISeries<double> input, int period**)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#examples)

```jsx-150469391 csharp
// Evaluates if the current bar **FOSC** is above zero
if (FOSC(14)[0] > 0)
   Print("FOSC is above zero indicating prices may rise");

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/forecast_oscillator_fosc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.