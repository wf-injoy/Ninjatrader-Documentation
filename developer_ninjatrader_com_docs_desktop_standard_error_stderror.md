## [Description](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#description)

The standard error of a method of measurement or estimation is the standard deviation of the sampling distribution associated with the estimation method. The term may also be used to refer to an estimate of that standard deviation, derived from a particular sample used to compute the estimate.

... Courtesy of [Wikipedia](http://en.wikipedia.org/wiki/Standard_error_(statistics))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#syntax)

`StdError(int period)`

`StdError(ISeries<double> input, int period)`

**Returns default value which is the mid line (also known as linear regression)**

`StdError(int period)[int barsAgo]`

`StdError(ISeries<double> input, int period)[int barsAgo]`

**Returns upper value**

`StdError(int period).Upper[int barsAgo]`

`StdError(ISeries<double> input, int period).Upper[int barsAgo]`

**Returns lower value**

`StdError(int period).Lower[int barsAgo]`

`StdError(ISeries<double> input, int period).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#examples)

```jsx-150469391 csharp
// Prints the current upper value of a 20 period **StdError** using default price type
double value = StdError(20).Upper[0];
Print("The current upper Standard Error value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#description)

The standard error of a method of measurement or estimation is the standard deviation of the sampling distribution associated with the estimation method. The term may also be used to refer to an estimate of that standard deviation, derived from a particular sample used to compute the estimate.

... Courtesy of [Wikipedia](http://en.wikipedia.org/wiki/Standard_error_(statistics))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#syntax)

`StdError(int period)`

`StdError(ISeries<double> input, int period)`

**Returns default value which is the mid line (also known as linear regression)**

`StdError(int period)[int barsAgo]`

`StdError(ISeries<double> input, int period)[int barsAgo]`

**Returns upper value**

`StdError(int period).Upper[int barsAgo]`

`StdError(ISeries<double> input, int period).Upper[int barsAgo]`

**Returns lower value**

`StdError(int period).Lower[int barsAgo]`

`StdError(ISeries<double> input, int period).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#examples)

```jsx-150469391 csharp
// Prints the current upper value of a 20 period **StdError** using default price type
double value = StdError(20).Upper[0];
Print("The current upper Standard Error value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/standard_error_stderror\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.