## [Definition](https://developer.ninjatrader.com/docs/desktop/value\#definition)

A collection of historical references to the first ISeries object Values\[0\] in the indicator. This is the primary indicator value (synched to the primary series in case of a [MultiSeries](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) indicator)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/value\#property-value)

An ISeries< `double` > object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/value\#syntax)

`Value`

## [Examples](https://developer.ninjatrader.com/docs/desktop/value\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a custom indicator
protected override void OnBarUpdate()
{
    // Ensures we have enough bars loaded for our indicator
    if (CurrentBar < 1)
        return;

    // Evaluates the indicator primary value 1 bar ago and sets the value of the indicator
    // for the current bar being evaluated
    if (Value[1] < High[0] - Low[0])
        Value[0] = High[0] - Low[0];
    else
        Value[0] = High[0] - Close[0];
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/value\#definition)

A collection of historical references to the first ISeries object Values\[0\] in the indicator. This is the primary indicator value (synched to the primary series in case of a [MultiSeries](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) indicator)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/value\#property-value)

An ISeries< `double` > object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/value\#syntax)

`Value`

## [Examples](https://developer.ninjatrader.com/docs/desktop/value\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a custom indicator
protected override void OnBarUpdate()
{
    // Ensures we have enough bars loaded for our indicator
    if (CurrentBar < 1)
        return;

    // Evaluates the indicator primary value 1 bar ago and sets the value of the indicator
    // for the current bar being evaluated
    if (Value[1] < High[0] - Low[0])
        Value[0] = High[0] - Low[0];
    else
        Value[0] = High[0] - Close[0];
}

```