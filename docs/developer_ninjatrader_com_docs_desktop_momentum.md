## [Description](https://developer.ninjatrader.com/docs/desktop/momentum\#description)

By measuring the amount that a security's price has changed over a given time span, the Momentum indicator provides an indication of a market's velocity and to some degree, a measure of the extent to which a trend still holds true. It can also be helpful in spotting likely reversal points.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/momentum\#syntax)

`Momentum(int period)`

`Momentum(ISeries<double> input, int period)`

**Returns default value**

`Momentum(int period)[int barsAgo]`

`Momentum(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/momentum\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/momentum\#parameters)

| Parameter | Description |
| --- | --- |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/momentum\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period Momentum using default price type
double value = Momentum(20)[0];
Print("The current Momentum value is " + value.ToString());

// Prints the current value of a 20 period Momentum using high price type
double value = Momentum(High, 20)[0];
Print("The current Momentum value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/momentum\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/momentum\#description)

By measuring the amount that a security's price has changed over a given time span, the Momentum indicator provides an indication of a market's velocity and to some degree, a measure of the extent to which a trend still holds true. It can also be helpful in spotting likely reversal points.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/momentum\#syntax)

`Momentum(int period)`

`Momentum(ISeries<double> input, int period)`

**Returns default value**

`Momentum(int period)[int barsAgo]`

`Momentum(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/momentum\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/momentum\#parameters)

| Parameter | Description |
| --- | --- |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/momentum\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period Momentum using default price type
double value = Momentum(20)[0];
Print("The current Momentum value is " + value.ToString());

// Prints the current value of a 20 period Momentum using high price type
double value = Momentum(High, 20)[0];
Print("The current Momentum value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/momentum\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.