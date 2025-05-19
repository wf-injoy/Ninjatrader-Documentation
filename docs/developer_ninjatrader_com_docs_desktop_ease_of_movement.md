## [Description](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#description)

The Ease of Movement indicator was designed to illustrate the relationship between volume and price change. It shows how much volume is required to move prices.

High Ease of Movement values occur when prices are moving upward with light volume. Low values occur when prices are moving downward on light volume. If prices are not moving or if heavy volume is required to move prices then the indicator will read near zero. A buy signal is produced when it crosses above zero. A sell signal is produced when the indicator crosses below zero (prices are moving downward more easily).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#syntax)

`EaseOfMovement(int smoothing, int volumeDivisor)`

`EaseOfMovement(ISeries<double> input, int smoothing, int volumeDivisor)`

**Returns default value**

`EaseOfMovement(int smoothing, int volumeDivisor)[int barsAgo]`

`EaseOfMovement(ISeries<double> input, int smoothing, int volumeDivisor)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| smoothing | The number of bars used to smooth the signal |
| volumeDivisor | The value used to calculate the box ratio |

## [Examples](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#examples)

```jsx-150469391 csharp
// Prints the current value of Ease of Movement using default price type
double value = EaseOfMovement(14, 10000)[0];
Print("The current Ease of Movement value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#description)

The Ease of Movement indicator was designed to illustrate the relationship between volume and price change. It shows how much volume is required to move prices.

High Ease of Movement values occur when prices are moving upward with light volume. Low values occur when prices are moving downward on light volume. If prices are not moving or if heavy volume is required to move prices then the indicator will read near zero. A buy signal is produced when it crosses above zero. A sell signal is produced when the indicator crosses below zero (prices are moving downward more easily).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#syntax)

`EaseOfMovement(int smoothing, int volumeDivisor)`

`EaseOfMovement(ISeries<double> input, int smoothing, int volumeDivisor)`

**Returns default value**

`EaseOfMovement(int smoothing, int volumeDivisor)[int barsAgo]`

`EaseOfMovement(ISeries<double> input, int smoothing, int volumeDivisor)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| smoothing | The number of bars used to smooth the signal |
| volumeDivisor | The value used to calculate the box ratio |

## [Examples](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#examples)

```jsx-150469391 csharp
// Prints the current value of Ease of Movement using default price type
double value = EaseOfMovement(14, 10000)[0];
Print("The current Ease of Movement value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/ease_of_movement\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.