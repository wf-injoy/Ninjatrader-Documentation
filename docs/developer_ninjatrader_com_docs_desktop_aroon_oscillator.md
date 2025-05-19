## [Description](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#description)

A trend-following indicator that uses aspects of the Aroon indicator ("Aroon up" and "Aroon down") to gauge the strength of a current trend and the likelihood that it will continue. The Aroon oscillator is calculated by subtracting Aroon down from Aroon up. Readings above zero indicate that an uptrend is present, while readings below zero indicate that a downtrend is present.

Courtesy of [Investopedia](http://investopedia.com/terms/a/aroonoscillator.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#syntax)

`AroonOscillator(int period)`

`AroonOscillator(ISeries<double> input, int period)`

**Returns default value**

`AroonOscillator(int period)[int barsAgo]`

`AroonOscillator(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current values of a 20 period AroonOscillator using default price type
double upValue = AroonOscillator(20)[0];
Print("The current AroonOscillator value is " + upValue.ToString());

// Prints the current values of a 20 period AroonOscillator using high price type
double upValue = AroonOscillator(High, 20)[0];
Print("The current AroonOscillator value is " + upValue.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#description)

A trend-following indicator that uses aspects of the Aroon indicator ("Aroon up" and "Aroon down") to gauge the strength of a current trend and the likelihood that it will continue. The Aroon oscillator is calculated by subtracting Aroon down from Aroon up. Readings above zero indicate that an uptrend is present, while readings below zero indicate that a downtrend is present.

Courtesy of [Investopedia](http://investopedia.com/terms/a/aroonoscillator.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#syntax)

`AroonOscillator(int period)`

`AroonOscillator(ISeries<double> input, int period)`

**Returns default value**

`AroonOscillator(int period)[int barsAgo]`

`AroonOscillator(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#examples)

```jsx-150469391 csharp
// Prints the current values of a 20 period AroonOscillator using default price type
double upValue = AroonOscillator(20)[0];
Print("The current AroonOscillator value is " + upValue.ToString());

// Prints the current values of a 20 period AroonOscillator using high price type
double upValue = AroonOscillator(High, 20)[0];
Print("The current AroonOscillator value is " + upValue.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/aroon_oscillator\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.