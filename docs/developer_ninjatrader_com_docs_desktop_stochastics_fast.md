## [Description](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#description)

Developed by George C. Lane in the late 1950s, the Stochastic Oscillator is a momentum indicator that shows the location of the current close relative to the high/low range over a set number of periods. Closing levels that are consistently near the top of the range indicate accumulation (buying pressure) and those near the bottom of the range indicate distribution (selling pressure).

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/stochastic-oscillator-fast-slow-and-full)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#syntax)

`StochasticsFast(int periodD, int periodK)`

`StochasticsFast(ISeries<double> input, int periodD, int periodK)`

**Returns %D value**

`StochasticsFast(int periodD, int periodK).D[int barsAgo]`

`StochasticsFast(ISeries<double> input, int periodD, int periodK).D[int barsAgo]`

**Returns %K value**

`StochasticsFast(int periodD, int periodK).K[int barsAgo]`

`StochasticsFast(ISeries<double> input, int periodD, int periodK).K[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| periodD | The period for the moving average of periodD |
| periodK | The period for the moving average of periodK |

## [Examples](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#examples)

```jsx-150469391 csharp
// Prints the current %D value
double value = StochasticsFast(3, 14).D[0];
Print("The current StochasticsFast %D value is " + value.ToString());

// Prints the current %K value
double value = StochasticsFast(3, 14).K[0];
Print("The current StochasticsFast %K value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#description)

Developed by George C. Lane in the late 1950s, the Stochastic Oscillator is a momentum indicator that shows the location of the current close relative to the high/low range over a set number of periods. Closing levels that are consistently near the top of the range indicate accumulation (buying pressure) and those near the bottom of the range indicate distribution (selling pressure).

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/stochastic-oscillator-fast-slow-and-full)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#syntax)

`StochasticsFast(int periodD, int periodK)`

`StochasticsFast(ISeries<double> input, int periodD, int periodK)`

**Returns %D value**

`StochasticsFast(int periodD, int periodK).D[int barsAgo]`

`StochasticsFast(ISeries<double> input, int periodD, int periodK).D[int barsAgo]`

**Returns %K value**

`StochasticsFast(int periodD, int periodK).K[int barsAgo]`

`StochasticsFast(ISeries<double> input, int periodD, int periodK).K[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| periodD | The period for the moving average of periodD |
| periodK | The period for the moving average of periodK |

## [Examples](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#examples)

```jsx-150469391 csharp
// Prints the current %D value
double value = StochasticsFast(3, 14).D[0];
Print("The current StochasticsFast %D value is " + value.ToString());

// Prints the current %K value
double value = StochasticsFast(3, 14).K[0];
Print("The current StochasticsFast %K value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/stochastics_fast\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.