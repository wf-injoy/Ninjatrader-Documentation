## [Description](https://developer.ninjatrader.com/docs/desktop/maximum_max\#description)

Returns the highest value over the specified period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maximum_max\#syntax)

`MAX(int period)`

`MAX(ISeries<double> input, int period)`

**Returns default value**

`MAX(int period)[int barsAgo]`

`MAX(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/maximum_max\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/maximum_max\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/maximum_max\#examples)

```jsx-150469391 csharp
// Prints the highest high value over the last 20 periods
double value = MAX(High, 20)[0];
Print("The current MAX value is " + value.ToString());

// Note the above call with a barsAgo of 0 includes the current MAX of the input high series in the value. If we want to check for example for a break of this value, storing the last bar's MAX would be needed.
double value = MAX(High, 20)[1];

if (High[0] > value)
    Draw.ArrowUp(this, CurrentBar.ToString(), true, 0, Low[0] - TickSize, Brushes.Blue);

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/maximum_max\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/maximum_max\#description)

Returns the highest value over the specified period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maximum_max\#syntax)

`MAX(int period)`

`MAX(ISeries<double> input, int period)`

**Returns default value**

`MAX(int period)[int barsAgo]`

`MAX(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/maximum_max\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/maximum_max\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/maximum_max\#examples)

```jsx-150469391 csharp
// Prints the highest high value over the last 20 periods
double value = MAX(High, 20)[0];
Print("The current MAX value is " + value.ToString());

// Note the above call with a barsAgo of 0 includes the current MAX of the input high series in the value. If we want to check for example for a break of this value, storing the last bar's MAX would be needed.
double value = MAX(High, 20)[1];

if (High[0] > value)
    Draw.ArrowUp(this, CurrentBar.ToString(), true, 0, Low[0] - TickSize, Brushes.Blue);

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/maximum_max\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.