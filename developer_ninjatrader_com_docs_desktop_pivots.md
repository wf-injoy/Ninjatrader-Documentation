## [Description](https://developer.ninjatrader.com/docs/desktop/pivots\#description)

The pivot point is used as a predictive indicator. If the following day's market price falls below the pivot point, it may be used as a new resistance level. Conversely, if the market price rises above the pivot point, it may act as the new support level.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/04/041404.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/pivots\#syntax)

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

**Returns pivot point value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).Pp[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).PP[int barsAgo]`

**Returns R1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

**Returns R2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

**Returns R3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

**Returns S1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

**Returns S2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

**Returns S3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/pivots\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/pivots\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| pivotRangeType | Sets the range for the type of pivot calculated. Possible values are: **PivotRange.Daily**, **PivotRange.Weekly**, **PivotRange.Monthly** |
| priorDayHLC | Sets how the prior range High, Low, Close values are calculated. Possible values are: **HLCCalculationMode.CalcFromIntradayData**, **HLCCalculationMode.DailyBars**, **HLCCalculationMode.UserDefinedValues** |
| userDefinedClose | Sets the close for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| userDefinedHigh | Sets the high for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| userDefinedLow | Sets the low for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| width | Sets how long the Pivots lines will be drawn |

## [Examples](https://developer.ninjatrader.com/docs/desktop/pivots\#examples)

```jsx-150469391 csharp
// Prints the current pivot point value
double value = Pivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).Pp[0];
Print("The current Pivots' pivot value is " + value.ToString());

// Prints the current S2 pivot value
double value = Pivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).S2[0];
Print("The current Pivots' S2 pivot value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/pivots\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## Note

When using **HLCCalculationMode.DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use **. [IsValidDataPoint()](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint)** as a check:

```jsx-150469391 csharp
// Evaluates that this is a valid pivot point value
if (Pivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp.IsValidDataPoint(0))
{
     // Prints the current pivot point value
     double value = Pivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp[0];
     Print("The current Pivots' pivot value is " + value.ToString());
}

```

## [Description](https://developer.ninjatrader.com/docs/desktop/pivots\#description)

The pivot point is used as a predictive indicator. If the following day's market price falls below the pivot point, it may be used as a new resistance level. Conversely, if the market price rises above the pivot point, it may act as the new support level.

... Courtesy of [Investopedia](http://www.investopedia.com/articles/technical/04/041404.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/pivots\#syntax)

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

**Returns pivot point value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).Pp[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).PP[int barsAgo]`

**Returns R1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

**Returns R2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

**Returns R3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

**Returns S1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

**Returns S2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

**Returns S3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/pivots\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/pivots\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| pivotRangeType | Sets the range for the type of pivot calculated. Possible values are: **PivotRange.Daily**, **PivotRange.Weekly**, **PivotRange.Monthly** |
| priorDayHLC | Sets how the prior range High, Low, Close values are calculated. Possible values are: **HLCCalculationMode.CalcFromIntradayData**, **HLCCalculationMode.DailyBars**, **HLCCalculationMode.UserDefinedValues** |
| userDefinedClose | Sets the close for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| userDefinedHigh | Sets the high for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| userDefinedLow | Sets the low for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| width | Sets how long the Pivots lines will be drawn |

## [Examples](https://developer.ninjatrader.com/docs/desktop/pivots\#examples)

```jsx-150469391 csharp
// Prints the current pivot point value
double value = Pivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).Pp[0];
Print("The current Pivots' pivot value is " + value.ToString());

// Prints the current S2 pivot value
double value = Pivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).S2[0];
Print("The current Pivots' S2 pivot value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/pivots\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## Note

When using **HLCCalculationMode.DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use **. [IsValidDataPoint()](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint)** as a check:

```jsx-150469391 csharp
// Evaluates that this is a valid pivot point value
if (Pivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp.IsValidDataPoint(0))
{
     // Prints the current pivot point value
     double value = Pivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp[0];
     Print("The current Pivots' pivot value is " + value.ToString());
}

```