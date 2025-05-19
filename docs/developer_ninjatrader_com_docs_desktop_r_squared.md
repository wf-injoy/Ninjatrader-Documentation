## [Description](https://developer.ninjatrader.com/docs/desktop/r_squared\#description)

The **r-squared** indicator calculates how well the price approximates a linear regression line. The indicator gets its name from the calculation, which is, the square of the correlation coefficient (referred to in mathematics by the Greek letter rho, or r). The range of the **r-squared** is from zero to one.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=rsquared.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/r_squared\#syntax)

`RSquared(int period)`

`RSquared(ISeries<double> input, int period)`

**Returns default value**

`RSquared(int period)[int barsAgo]`

`RSquared(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/r_squared\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/r_squared\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series<\`T>](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/r_squared\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period R-squared using default price type
double value = RSquared(20)[0];
Print("The current R-squared value is " + value.ToString());

// Prints the current value of a 20 period R-squared using high price type
double value = RSquared(High, 20)[0];
Print("The current R-squared value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/r_squared\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/r_squared\#description)

The **r-squared** indicator calculates how well the price approximates a linear regression line. The indicator gets its name from the calculation, which is, the square of the correlation coefficient (referred to in mathematics by the Greek letter rho, or r). The range of the **r-squared** is from zero to one.

... Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=rsquared.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/r_squared\#syntax)

`RSquared(int period)`

`RSquared(ISeries<double> input, int period)`

**Returns default value**

`RSquared(int period)[int barsAgo]`

`RSquared(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/r_squared\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/r_squared\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series<\`T>](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/r_squared\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period R-squared using default price type
double value = RSquared(20)[0];
Print("The current R-squared value is " + value.ToString());

// Prints the current value of a 20 period R-squared using high price type
double value = RSquared(High, 20)[0];
Print("The current R-squared value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/r_squared\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.