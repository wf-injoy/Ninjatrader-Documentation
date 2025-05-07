## [Description](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#description)

Woodies CCI Club pivots indicator.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#syntax)

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width)`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width)`

**Returns pivot point value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).PP[int barsAgo]`

`WoodiesPivotsISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).PP[int barsAgo]`

**Returns R1 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).R1[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).R1[int barsAgo]`

**Returns R2 value**

WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).R2\[int barsAgo\]

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).R2[int barsAgo]`

**Returns S1 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).S1[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).S1[int barsAgo]`

**Returns S2 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).S2[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).S2[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| priorDayHLC | Sets how the prior range High, Low, Close values are calculated. Possible values are:<br>- HLCCalculationModeWoodie.CalcFromIntradayData<br>  <br>- HLCCalculationModeWoodie.DailyBars<br>  <br>- HLCCalculationModeWoodie.UserDefinedValues |
| width | An int determining the width of the pivot values plotted |

## [Example](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#example)

```jsx-150469391 csharp
// Prints the current pivot point value
double ppValue = WoodiesPivots(HLCCalculationModeWoodie.CalcFromIntradayData, 20).PP[0];
Print("The current Woodies Pivots' pivot value is " + ppValue);

// Prints the current S2 pivot value
double s2Value = WoodiesPivots(HLCCalculationModeWoodie.CalcFromIntradayData, 20).S2[0];
Print("The current Woodies Pivots' S2 pivot value is " + s2Value);

```

## Note

Tip: When using HLCCalculationMode. **DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use [.IsValidDataPoint()](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint) as a check.

```jsx-150469391 csharp
// Evaluates that this is a valid Woodies Pivots value
if (WoodiesPivots(HLCCalculationModeWoodie.DailyBars, 20).PP.IsValidDataPoint(0))
{
    // Prints the current pivot point value
    double value = WoodiesPivots(HLCCalculationModeWoodie.DailyBars, 20).PP[0];
    Print("The current Woodies Pivots' pivot value is " + value.ToString());
}

```

## [Description](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#description)

Woodies CCI Club pivots indicator.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#syntax)

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width)`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width)`

**Returns pivot point value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).PP[int barsAgo]`

`WoodiesPivotsISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).PP[int barsAgo]`

**Returns R1 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).R1[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).R1[int barsAgo]`

**Returns R2 value**

WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).R2\[int barsAgo\]

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).R2[int barsAgo]`

**Returns S1 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).S1[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).S1[int barsAgo]`

**Returns S2 value**

`WoodiesPivots(HLCCalculationModeWoodie priorDayHLC, int width).S2[int barsAgo]`

`WoodiesPivots(ISeries<double> input, HLCCalculationModeWoodie priorDayHLC, int width).S2[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| priorDayHLC | Sets how the prior range High, Low, Close values are calculated. Possible values are:<br>- HLCCalculationModeWoodie.CalcFromIntradayData<br>  <br>- HLCCalculationModeWoodie.DailyBars<br>  <br>- HLCCalculationModeWoodie.UserDefinedValues |
| width | An int determining the width of the pivot values plotted |

## [Example](https://developer.ninjatrader.com/docs/desktop/woodies_pivots\#example)

```jsx-150469391 csharp
// Prints the current pivot point value
double ppValue = WoodiesPivots(HLCCalculationModeWoodie.CalcFromIntradayData, 20).PP[0];
Print("The current Woodies Pivots' pivot value is " + ppValue);

// Prints the current S2 pivot value
double s2Value = WoodiesPivots(HLCCalculationModeWoodie.CalcFromIntradayData, 20).S2[0];
Print("The current Woodies Pivots' S2 pivot value is " + s2Value);

```

## Note

Tip: When using HLCCalculationMode. **DailyBars** it can be expected that a value of 0 is returned when the daily bars have not been loaded yet. Due to the asynchronous nature of this indicator calling daily bars you should only access the pivot values when the indicator has loaded all required Bars objects. To ensure you are accessing accurate values you can use [.IsValidDataPoint()](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint) as a check.

```jsx-150469391 csharp
// Evaluates that this is a valid Woodies Pivots value
if (WoodiesPivots(HLCCalculationModeWoodie.DailyBars, 20).PP.IsValidDataPoint(0))
{
    // Prints the current pivot point value
    double value = WoodiesPivots(HLCCalculationModeWoodie.DailyBars, 20).PP[0];
    Print("The current Woodies Pivots' pivot value is " + value.ToString());
}

```