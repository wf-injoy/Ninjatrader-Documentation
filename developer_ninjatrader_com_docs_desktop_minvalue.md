## [Definition](https://developer.ninjatrader.com/docs/desktop/minvalue\#definition)

The minimum value used for the automatic scaling of the y axis. This property will only be used when the chart object is set to **IsAutoScale**.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/minvalue\#property-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/minvalue\#syntax)

`MinValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/minvalue\#examples)

```jsx-150469391 csharp

public override void OnCalculateMinMax()
{
   if (DrawingState != DrawingState.Building)
   {
     //set the minimum value to the chart anchors price
     MinValue = Anchor.Price;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/minvalue\#definition)

The minimum value used for the automatic scaling of the y axis. This property will only be used when the chart object is set to **IsAutoScale**.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/minvalue\#property-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/minvalue\#syntax)

`MinValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/minvalue\#examples)

```jsx-150469391 csharp

public override void OnCalculateMinMax()
{
   if (DrawingState != DrawingState.Building)
   {
     //set the minimum value to the chart anchors price
     MinValue = Anchor.Price;
   }
}

```