## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#description)

The triple exponential average (TRIX) indicator is an oscillator used to identify oversold and overbought markets, and it can also be used as a momentum indicator.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/02/092402.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#syntax)

`TRIX(int period, int signalPeriod)`

`TRIX(ISeries<double> input, int period, int signalPeriod)`

**Returns trix value**

`TRIX(int period, int signalPeriod)[int barsAgo]`

`TRIX(ISeries<double> input, int period, int signalPeriod)[int barsAgo]`

**Returns signal value**

`TRIX(int period, int signalPeriod).Signal[int barsAgo]`

`TRIX(ISeries<double> input, int period, int signalPeriod).Signal[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| signalPeriod | Period for signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TRIX using default price type
double value = TRIX(20, 3).Default[0];
Print("The current TRIX value is " + value.ToString());

// Prints the current signal value of a 20 period TRIX using high price type
double value = TRIX(High, 20, 3).Signal[0];
Print("The current TRIX signal value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#description)

The triple exponential average (TRIX) indicator is an oscillator used to identify oversold and overbought markets, and it can also be used as a momentum indicator.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/02/092402.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#syntax)

`TRIX(int period, int signalPeriod)`

`TRIX(ISeries<double> input, int period, int signalPeriod)`

**Returns trix value**

`TRIX(int period, int signalPeriod)[int barsAgo]`

`TRIX(ISeries<double> input, int period, int signalPeriod)[int barsAgo]`

**Returns signal value**

`TRIX(int period, int signalPeriod).Signal[int barsAgo]`

`TRIX(ISeries<double> input, int period, int signalPeriod).Signal[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| signalPeriod | Period for signal line |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period TRIX using default price type
double value = TRIX(20, 3).Default[0];
Print("The current TRIX value is " + value.ToString());

// Prints the current signal value of a 20 period TRIX using high price type
double value = TRIX(High, 20, 3).Signal[0];
Print("The current TRIX signal value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_triple_exponential_trix\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.