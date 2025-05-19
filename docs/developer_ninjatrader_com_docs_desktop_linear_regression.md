## [Description](https://developer.ninjatrader.com/docs/desktop/linear_regression\#description)

The Linear Regression Indicator plots the trend of a security's price over time. That trend is determined by calculating a Linear Regression Trendline using the least squares method. This ensures the minimum distance between the data points and a Linear Regression Trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/linear_regression\#syntax)

`LinReg(int period)`

`LinReg(ISeries<double> input, int period)`

**Returns default value**

`LinReg(int period)[int barsAgo]`

`LinReg(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/linear_regression\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/linear_regression\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/linear_regression\#examples)

```jsx-150469391 csharp

// Prints the current value of a 20 period LinReg using default price type
double value = LinReg(20)[0];
Print("The current LinReg value is " + value.ToString());

// Prints the current value of a 20 period LinReg using high price type
double value = LinReg(High, 20)[0];
Print("The current LinReg value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/linear_regression\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/linear_regression\#description)

The Linear Regression Indicator plots the trend of a security's price over time. That trend is determined by calculating a Linear Regression Trendline using the least squares method. This ensures the minimum distance between the data points and a Linear Regression Trendline.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/linear_regression\#syntax)

`LinReg(int period)`

`LinReg(ISeries<double> input, int period)`

**Returns default value**

`LinReg(int period)[int barsAgo]`

`LinReg(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/linear_regression\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/linear_regression\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/linear_regression\#examples)

```jsx-150469391 csharp

// Prints the current value of a 20 period LinReg using default price type
double value = LinReg(20)[0];
Print("The current LinReg value is " + value.ToString());

// Prints the current value of a 20 period LinReg using high price type
double value = LinReg(High, 20)[0];
Print("The current LinReg value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/linear_regression\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.