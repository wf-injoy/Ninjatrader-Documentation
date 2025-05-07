## [Definition](https://developer.ninjatrader.com/docs/desktop/values\#definition)

Holds an array of **ISeries< `double` >** objects holding hold the indicator's underlying calculated values. ISeries< `double` \> values are added to this array when calling the [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) method. In case of a [MultiSeries](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) indicator synched to the primary series.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/values\#property-value)

A collection of **ISeries< `double` >** objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/values\#syntax)

`Values[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/values\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a custom indicator
protected override void OnBarUpdate()
{
    // Ensures we have enough bars loaded for our indicator
    if (CurrentBar < 1)
        return;

    // Evaluates the indicator's secondary value 1 bar ago and sets the value of the indicator
    // for the current bar being evaluated
    if (Values[1][1] < High[0] - Low[0])
        Value[0] = High[0] - Low[0];
    else
        Value[0] = High[0] - Close[0];
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/values\#definition)

Holds an array of **ISeries< `double` >** objects holding hold the indicator's underlying calculated values. ISeries< `double` \> values are added to this array when calling the [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) method. In case of a [MultiSeries](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) indicator synched to the primary series.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/values\#property-value)

A collection of **ISeries< `double` >** objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/values\#syntax)

`Values[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/values\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a custom indicator
protected override void OnBarUpdate()
{
    // Ensures we have enough bars loaded for our indicator
    if (CurrentBar < 1)
        return;

    // Evaluates the indicator's secondary value 1 bar ago and sets the value of the indicator
    // for the current bar being evaluated
    if (Values[1][1] < High[0] - Low[0])
        Value[0] = High[0] - Low[0];
    else
        Value[0] = High[0] - Close[0];
}

```