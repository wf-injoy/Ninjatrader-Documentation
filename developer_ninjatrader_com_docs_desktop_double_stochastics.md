## [Description](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#description)

Double Stochastics is a variation of the **Stochastics** indicator developed by William Blau.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#syntax)

`DoubleStochastics(int period)`

`DoubleStochastics(ISeries<double> input, int period)`

**Returns default value**

`DoubleStochastics(int period)[int barsAgo]`

`DoubleStochastics(ISeries<double> input, int period)[int barsAgo]`

**Returns %K value**

`DoubleStochastics(int period).K[int barsAgo]`

`DoubleStochastics(ISeries<double> input, int period).K[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#examples)

```jsx-150469391 csharp
// Prints the current value
double value = DoubleStochastics(10)[0];
Print("The current Double Stochastics value is " + value.ToString());

// Prints the current %K value
double value = DoubleStochastics(10).K[0];
Print("The current Double Stochastics %K value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#description)

Double Stochastics is a variation of the **Stochastics** indicator developed by William Blau.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#syntax)

`DoubleStochastics(int period)`

`DoubleStochastics(ISeries<double> input, int period)`

**Returns default value**

`DoubleStochastics(int period)[int barsAgo]`

`DoubleStochastics(ISeries<double> input, int period)[int barsAgo]`

**Returns %K value**

`DoubleStochastics(int period).K[int barsAgo]`

`DoubleStochastics(ISeries<double> input, int period).K[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#examples)

```jsx-150469391 csharp
// Prints the current value
double value = DoubleStochastics(10)[0];
Print("The current Double Stochastics value is " + value.ToString());

// Prints the current %K value
double value = DoubleStochastics(10).K[0];
Print("The current Double Stochastics %K value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/double_stochastics\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.