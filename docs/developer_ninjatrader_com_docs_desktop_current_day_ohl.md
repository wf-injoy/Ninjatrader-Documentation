## [Description](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#description)

The current day (session) open, high and low values.

## Note

Only use this indicator on intraday series.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#syntax)

`CurrentDayOHL()`

`CurrentDayOHL(ISeries<double> input)`

**Returns current session open value**

`CurrentDayOHL().CurrentOpen[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentOpen[int barsAgo]`

**Returns current session high value**

`CurrentDayOHL().CurrentHigh[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentHigh[int barsAgo]`

**Returns current session low value**

`CurrentDayOHL().CurrentLow[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentLow[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#examples)

```jsx-150469391 csharp
// Prints the current value of the session low
double value = CurrentDayOHL().CurrentLow[0];
Print("The current session low value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#description)

The current day (session) open, high and low values.

## Note

Only use this indicator on intraday series.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#syntax)

`CurrentDayOHL()`

`CurrentDayOHL(ISeries<double> input)`

**Returns current session open value**

`CurrentDayOHL().CurrentOpen[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentOpen[int barsAgo]`

**Returns current session high value**

`CurrentDayOHL().CurrentHigh[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentHigh[int barsAgo]`

**Returns current session low value**

`CurrentDayOHL().CurrentLow[int barsAgo]`

`CurrentDayOHL(ISeries<double> input).CurrentLow[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#examples)

```jsx-150469391 csharp
// Prints the current value of the session low
double value = CurrentDayOHL().CurrentLow[0];
Print("The current session low value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/current_day_ohl\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.