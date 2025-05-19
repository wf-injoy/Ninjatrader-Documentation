## [Definition](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#definition)

Copies the **ChartAnchor** time and price values from one anchor to another. This includes the **BarsAgo**, **SlotIndex**, **Time**, **Price**, and **DrawnOnBar** values. This method is useful for updating a chart anchor to a recent data point when the user interacts with the drawing chart anchor.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#syntax)

`<chartanchor>.CopyDataValues(ChartAnchor toAnchor)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#method-parameters)

| toAnchor | The ChartAnchor to copy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#examples)

```jsx-150469391 csharp

public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   // if the user is moving the draw object, copy the most recent dataPoint to MyAnchor
   if (DrawingState == DrawingState.Moving)
     dataPoint.CopyDataValues(Anchor);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#definition)

Copies the **ChartAnchor** time and price values from one anchor to another. This includes the **BarsAgo**, **SlotIndex**, **Time**, **Price**, and **DrawnOnBar** values. This method is useful for updating a chart anchor to a recent data point when the user interacts with the drawing chart anchor.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#syntax)

`<chartanchor>.CopyDataValues(ChartAnchor toAnchor)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#method-parameters)

| toAnchor | The ChartAnchor to copy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/copydatavalues\#examples)

```jsx-150469391 csharp

public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   // if the user is moving the draw object, copy the most recent dataPoint to MyAnchor
   if (DrawingState == DrawingState.Moving)
     dataPoint.CopyDataValues(Anchor);

```