## [Description](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#description)

Camarilla pivots are a price analysis tool that generates potential support and resistance levels by multiplying the prior range then adding or subtracting it from the close.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#syntax)

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

**Returns R1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

**Returns R2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

**Returns R3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

**Returns R4 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R4[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R4[int barsAgo]`

**Returns S1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

**Returns S2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

\*\*Returns S3 value \*\*

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

**Returns S4 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S4[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S4[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **pivotRangeType** | Sets the range for the type of pivot calculated. Possible values are:<br>**PivotRange.Daily**<br>**PivotRange.Weekly**<br>**PivotRange.Monthly** |
| **priorDayHLC** | Sets how the prior range High, Low, Close values are calculated. Possible values are:<br>**HLCCalculationMode.CalcFromIntradayData**<br>**HLCCalculationMode.DailyBars**<br>**HLCCalculationMode.UserDefinedValues** |
| **userDefinedClose** | Sets the close for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **userDefinedHigh** | Sets the high for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **userDefinedLow** | Sets the low for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **width** | Sets how long the Pivots lines will be drawn |

## [Examples](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#examples)

```jsx-150469391 csharp
// Prints the current R1 pivot value
double valueR1 = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).R1[0];
Print("The current Camarilla Pivots' R1 value is " + valueR1.ToString());
// Prints the current S2 pivot value
double valueS2 = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).S2[0];
Print("The current Camarilla Pivots' S2 pivot value is " + valueS2.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## Note

- When using **HLCCalculationMode.DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use \*\*. [IsValidDataPoint()\*\*](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint) as a check:

```jsx-150469391 csharp
if (CamarillaPivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp.IsValidDataPoint(0))
{
    // Prints the current pivot point value
    double valuePp = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp[0];
    Print("The current Camarilla Pivots' pivot value is " + valuePp.ToString());
}

```

## [Description](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#description)

Camarilla pivots are a price analysis tool that generates potential support and resistance levels by multiplying the prior range then adding or subtracting it from the close.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#syntax)

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width)`

**Returns R1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R1[int barsAgo]`

**Returns R2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R2[int barsAgo]`

**Returns R3 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R3[int barsAgo]`

**Returns R4 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R4[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).R4[int barsAgo]`

**Returns S1 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S1[int barsAgo]`

**Returns S2 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S2[int barsAgo]`

\*\*Returns S3 value \*\*

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S3[int barsAgo]`

**Returns S4 value**

`Pivots(PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S4[int barsAgo]`

`Pivots(ISeries<double> input, PivotRange pivotRangeType, HLCCalculationMode priorDayHLC, double userDefinedClose, double userDefinedHigh, double userDefinedLow, int width).S4[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **pivotRangeType** | Sets the range for the type of pivot calculated. Possible values are:<br>**PivotRange.Daily**<br>**PivotRange.Weekly**<br>**PivotRange.Monthly** |
| **priorDayHLC** | Sets how the prior range High, Low, Close values are calculated. Possible values are:<br>**HLCCalculationMode.CalcFromIntradayData**<br>**HLCCalculationMode.DailyBars**<br>**HLCCalculationMode.UserDefinedValues** |
| **userDefinedClose** | Sets the close for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **userDefinedHigh** | Sets the high for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **userDefinedLow** | Sets the low for Pivots calculations when using **HLCCalculationMode.UserDefinedValues**. |
| **width** | Sets how long the Pivots lines will be drawn |

## [Examples](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#examples)

```jsx-150469391 csharp
// Prints the current R1 pivot value
double valueR1 = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).R1[0];
Print("The current Camarilla Pivots' R1 value is " + valueR1.ToString());
// Prints the current S2 pivot value
double valueS2 = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.CalcFromIntradayData, 0, 0, 0, 20).S2[0];
Print("The current Camarilla Pivots' S2 pivot value is " + valueS2.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/camarilla_pivots\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## Note

- When using **HLCCalculationMode.DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use \*\*. [IsValidDataPoint()\*\*](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint) as a check:

```jsx-150469391 csharp
if (CamarillaPivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp.IsValidDataPoint(0))
{
    // Prints the current pivot point value
    double valuePp = CamarillaPivots(PivotRange.Daily, HLCCalculationMode.DailyBars, 0, 0, 0, 20).Pp[0];
    Print("The current Camarilla Pivots' pivot value is " + valuePp.ToString());
}

```