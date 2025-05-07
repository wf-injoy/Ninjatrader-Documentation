## [Definition](https://developer.ninjatrader.com/docs/desktop/maxvalue\#definition)

The maximum value used for the automatic scaling of the y axis. This property will only be used when the chart object is set to \[isautoscale\].

## [Property Value](https://developer.ninjatrader.com/docs/desktop/maxvalue\#property-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maxvalue\#syntax)

`MaxValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/maxvalue\#examples)

```jsx-150469391 csharp

public override void OnCalculateMinMax()
{
    if (DrawingState != DrawingState.Building)
    {
        //set the maximum value to the chart anchors price
        MaxValue = Anchor.Price;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/maxvalue\#definition)

The maximum value used for the automatic scaling of the y axis. This property will only be used when the chart object is set to \[isautoscale\].

## [Property Value](https://developer.ninjatrader.com/docs/desktop/maxvalue\#property-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maxvalue\#syntax)

`MaxValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/maxvalue\#examples)

```jsx-150469391 csharp

public override void OnCalculateMinMax()
{
    if (DrawingState != DrawingState.Building)
    {
        //set the maximum value to the chart anchors price
        MaxValue = Anchor.Price;
    }
}

```