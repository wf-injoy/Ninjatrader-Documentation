## [Description](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#description)

The Linear Regression Intercept provides the intercept value of the **Linear Regression** trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#syntax)

`LinRegIntercept(int period)`

`LinRegIntercept(ISeries<double> input, int period)`

**Returns default value**

`LinRegIntercept(int period)[int barsAgo]`

`LinRegIntercept(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#return-value)

**double**; Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#examples)

```jsx-150469391 csharp
// Prints the current intercept value of a 20 period LinReg using default price type
double value = LinRegIntercept(20)[0];
Print("The current intercept value is " + value.ToString());
// Prints the current intercept value of a 20 period LinReg using high price type
double value = LinRegIntercept(High, 20)[0];
Print("The current intercept value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#description)

The Linear Regression Intercept provides the intercept value of the **Linear Regression** trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#syntax)

`LinRegIntercept(int period)`

`LinRegIntercept(ISeries<double> input, int period)`

**Returns default value**

`LinRegIntercept(int period)[int barsAgo]`

`LinRegIntercept(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#return-value)

**double**; Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#examples)

```jsx-150469391 csharp
// Prints the current intercept value of a 20 period LinReg using default price type
double value = LinRegIntercept(20)[0];
Print("The current intercept value is " + value.ToString());
// Prints the current intercept value of a 20 period LinReg using high price type
double value = LinRegIntercept(High, 20)[0];
Print("The current intercept value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/linear_regression_intercept\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.