## [Description](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#description)

Same as the **ADX** indicator with the addition of the +DI and -DI values.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/dmi.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#syntax)

`DM(int period)`

`DM(ISeries<double> input, int period)`

**Returns default ADX value**

`DM(int period)[int barsAgo]`

`DM(ISeries<double> input, int period)[int barsAgo]`

**Returns +DI value**

`DM(int period).DiPlus[int barsAgo]`

`DM(ISeries<double> input, int period).DiPlus[int barsAgo]`

**Returns -DI value**

`DM(int period).DiMinus[int barsAgo]`

`DM(ISeries<double> input, int period).DiMinus[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period +DI using default price type
double value = DM(20).DiPlus[0];
Print("The current +DI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#description)

Same as the **ADX** indicator with the addition of the +DI and -DI values.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/dmi.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#syntax)

`DM(int period)`

`DM(ISeries<double> input, int period)`

**Returns default ADX value**

`DM(int period)[int barsAgo]`

`DM(ISeries<double> input, int period)[int barsAgo]`

**Returns +DI value**

`DM(int period).DiPlus[int barsAgo]`

`DM(ISeries<double> input, int period).DiPlus[int barsAgo]`

**Returns -DI value**

`DM(int period).DiMinus[int barsAgo]`

`DM(ISeries<double> input, int period).DiMinus[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period +DI using default price type
double value = DM(20).DiPlus[0];
Print("The current +DI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/directional_movement_dm\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.