## [Description](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#description)

An indicator developed by J. Welles Wilder for identifying when a definable trend is present in an instrument. That is, the DMI tells whether an instrument is trending or not.

...Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=DX.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#syntax)

`DMI(int period)`

`DMI(ISeries<double> input, int period)`

**Returns default value**

`DMI(int period)[int barsAgo]`

`DMI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period DMI using default price type
double value = DMI(20)[0];
Print("The current DMI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#description)

An indicator developed by J. Welles Wilder for identifying when a definable trend is present in an instrument. That is, the DMI tells whether an instrument is trending or not.

...Courtesy of [FMLabs](http://www.fmlabs.com/reference/default.htm?url=DX.htm)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#syntax)

`DMI(int period)`

`DMI(ISeries<double> input, int period)`

**Returns default value**

`DMI(int period)[int barsAgo]`

`DMI(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period DMI using default price type
double value = DMI(20)[0];
Print("The current DMI value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/directional_movement_index_dmi\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.