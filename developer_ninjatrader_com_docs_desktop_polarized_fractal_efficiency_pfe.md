## [Description](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#description)

The Polarized Fractal Efficiency indicator uses fractal geometry to determine how efficiently the price is moving. When the **PFE** is zigzagging around zero, then the price is congested and not trending. When the **PFE** is smooth and above/below zero, then the price is in an up/down trend. The higher/lower the **PFE** value, the stronger the trend is.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=PFE.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#syntax)

`PFE(int period, int smooth)`

`PFE(ISeries<double> input, int period, int smooth)`

**Returns default value**

`PFE(int period, int smooth)[int barsAgo]`

`PFE(ISeries<double> input, int period, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| smooth | The smoothing factor to be applied |

## [Examples](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period PFE using default price type
double value = PFE(20, 2)[0];
Print("The current PFE value is " + value.ToString());

// Prints the current value of a 20 period PFE using high price type
double value = PFE(High, 20, 2)[0];
Print("The current PFE value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#description)

The Polarized Fractal Efficiency indicator uses fractal geometry to determine how efficiently the price is moving. When the **PFE** is zigzagging around zero, then the price is congested and not trending. When the **PFE** is smooth and above/below zero, then the price is in an up/down trend. The higher/lower the **PFE** value, the stronger the trend is.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=PFE.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#syntax)

`PFE(int period, int smooth)`

`PFE(ISeries<double> input, int period, int smooth)`

**Returns default value**

`PFE(int period, int smooth)[int barsAgo]`

`PFE(ISeries<double> input, int period, int smooth)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| smooth | The smoothing factor to be applied |

## [Examples](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period PFE using default price type
double value = PFE(20, 2)[0];
Print("The current PFE value is " + value.ToString());

// Prints the current value of a 20 period PFE using high price type
double value = PFE(High, 20, 2)[0];
Print("The current PFE value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/polarized_fractal_efficiency_pfe\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.