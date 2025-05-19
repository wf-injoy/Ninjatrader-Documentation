## [Description](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#description)

The Price Oscillator is an indicator based on the difference between two **moving averages**, and is expressed as either a percentage or in absolute terms.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_priceOscillator.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#syntax)

`PriceOscillator(int fast, int slow, int smooth)`

`PriceOscillator(ISeries<double> input, int fast, int slow, int smooth)`

**Returns default value**

`PriceOscillator(int fast, int slow, int smooth)[int barsAgo]`

`PriceOscillator(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| fast | The number of bars to calculate the fast **EMA** |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The number of bars to calculate the slow **EMA** |
| smooth | The number of bars to calculate the **EMA** signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period PriceOscillator using default price type
double value = PriceOscillator(12, 26, 9)[0];
Print("The current PriceOscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#description)

The Price Oscillator is an indicator based on the difference between two **moving averages**, and is expressed as either a percentage or in absolute terms.

... Courtesy of [StockCharts](http://stockcharts.com/education/IndicatorAnalysis/indic_priceOscillator.html)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#syntax)

`PriceOscillator(int fast, int slow, int smooth)`

`PriceOscillator(ISeries<double> input, int fast, int slow, int smooth)`

**Returns default value**

`PriceOscillator(int fast, int slow, int smooth)[int barsAgo]`

`PriceOscillator(ISeries<double> input, int fast, int slow, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| fast | The number of bars to calculate the fast **EMA** |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| slow | The number of bars to calculate the slow **EMA** |
| smooth | The number of bars to calculate the **EMA** signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period PriceOscillator using default price type
double value = PriceOscillator(12, 26, 9)[0];
Print("The current PriceOscillator value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/price_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.