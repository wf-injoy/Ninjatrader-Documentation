## [Description](https://developer.ninjatrader.com/docs/desktop/summation_sum\#description)

Returns the sum of the values taken over a specified period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/summation_sum\#syntax)

`SUM(int period)`

`SUM(ISeries<double> input, int period)`

**Returns default value**

`SUM(int period)[int barsAgo]`

`SUM(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/summation_sum\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/summation_sum\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/summation_sum\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period SUM using default price type
double value = SUM(20)[0];
Print("The current SUM value is " + value.ToString());

// Prints the current value of a 20 period SUM using high price type
double value = SUM(High, 20)[0];
Print("The current SUM value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/summation_sum\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/summation_sum\#description)

Returns the sum of the values taken over a specified period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/summation_sum\#syntax)

`SUM(int period)`

`SUM(ISeries<double> input, int period)`

**Returns default value**

`SUM(int period)[int barsAgo]`

`SUM(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/summation_sum\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/summation_sum\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/summation_sum\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period SUM using default price type
double value = SUM(20)[0];
Print("The current SUM value is " + value.ToString());

// Prints the current value of a 20 period SUM using high price type
double value = SUM(High, 20)[0];
Print("The current SUM value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/summation_sum\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.