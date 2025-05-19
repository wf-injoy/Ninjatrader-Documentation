## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#description)

The TEMA is a smoothing indicator. It was developed by Patrick Mulloy and is described in his article in the January, 1994 issue of Technical Analysis of Stocks and Commodities magazine.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#syntax)

`TEMA(int period)`

`TEMA(ISeries<double> input, int period)`

**Returns default value**

`TEMA(int period)[int barsAgo]`

`TEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TEMA using default price type
double value = TEMA(20)[0];
Print("The current TEMA value is " + value.ToString());

// Prints the current value of a 20 period TEMA using high price type
double value = TEMA(High, 20)[0];
Print("The current TEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#description)

The TEMA is a smoothing indicator. It was developed by Patrick Mulloy and is described in his article in the January, 1994 issue of Technical Analysis of Stocks and Commodities magazine.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#syntax)

`TEMA(int period)`

`TEMA(ISeries<double> input, int period)`

**Returns default value**

`TEMA(int period)[int barsAgo]`

`TEMA(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TEMA using default price type
double value = TEMA(20)[0];
Print("The current TEMA value is " + value.ToString());

// Prints the current value of a 20 period TEMA using high price type
double value = TEMA(High, 20)[0];
Print("The current TEMA value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_tema\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.