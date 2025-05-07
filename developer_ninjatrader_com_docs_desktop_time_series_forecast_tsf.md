## [Description](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#description)

The Time Series Forecast function displays the statistical trend of a security's price over a specified time period based on linear regression analysis. Instead of a straight linear regression trendline, the Time Series Forecast plots the last point of multiple linear regression trendlines. This is why this indicator may sometimes be referred to as the "moving linear regression" indicator or the "regression oscillator."

## [Syntax](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#syntax)

`TSF(int forecast, int period)`

`TSF(ISeries<double> input, int forecast, int period)`

**Returns default value**

`TSF(int forecast, int period)[int barsAgo]`

`TSF(ISeries<double> input, int forecast, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#return-value)

**double**; Accessing this method via an index value `int barsAgo` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#parameters)

| Parameter | Description |
| --- | --- |
| **forecast** | Forecast period |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TSF using default price type
double value = TSF(3, 20)[0];
Print("The current TSF value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#description)

The Time Series Forecast function displays the statistical trend of a security's price over a specified time period based on linear regression analysis. Instead of a straight linear regression trendline, the Time Series Forecast plots the last point of multiple linear regression trendlines. This is why this indicator may sometimes be referred to as the "moving linear regression" indicator or the "regression oscillator."

## [Syntax](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#syntax)

`TSF(int forecast, int period)`

`TSF(ISeries<double> input, int forecast, int period)`

**Returns default value**

`TSF(int forecast, int period)[int barsAgo]`

`TSF(ISeries<double> input, int forecast, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#return-value)

**double**; Accessing this method via an index value `int barsAgo` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#parameters)

| Parameter | Description |
| --- | --- |
| **forecast** | Forecast period |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TSF using default price type
double value = TSF(3, 20)[0];
Print("The current TSF value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/time_series_forecast_tsf\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.