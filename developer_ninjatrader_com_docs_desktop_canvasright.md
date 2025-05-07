## [Definition](https://developer.ninjatrader.com/docs/desktop/canvasright\#definition)

Indicates the x-coordinate (in pixels) of the end of the chart canvas area.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/canvasright\#property-value)

A double representing the end of the chart canvas area.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/canvasright\#syntax)

`<chartcontrol>.CanvasRight`

## [Examples](https://developer.ninjatrader.com/docs/desktop/canvasright\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Store the beginning and ending x-coordinates of the canvas area
   double canvasBeginCoordinate = chartControl.CanvasLeft;
   double canvasEndCoordinate = chartControl.CanvasRight;

   // Print the stored values
   Print(String.Format("Chart canvas begins at x-coordinate {0} and ends at x-coordinate {1}", canvasBeginCoordinate, canvasEndCoordinate));
}

```

Based on the image below, CanvasRight reveals that the chart canvas ends at x-coordinate 526.

## [Definition](https://developer.ninjatrader.com/docs/desktop/canvasright\#definition)

Indicates the x-coordinate (in pixels) of the end of the chart canvas area.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/canvasright\#property-value)

A double representing the end of the chart canvas area.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/canvasright\#syntax)

`<chartcontrol>.CanvasRight`

## [Examples](https://developer.ninjatrader.com/docs/desktop/canvasright\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Store the beginning and ending x-coordinates of the canvas area
   double canvasBeginCoordinate = chartControl.CanvasLeft;
   double canvasEndCoordinate = chartControl.CanvasRight;

   // Print the stored values
   Print(String.Format("Chart canvas begins at x-coordinate {0} and ends at x-coordinate {1}", canvasBeginCoordinate, canvasEndCoordinate));
}

```

Based on the image below, CanvasRight reveals that the chart canvas ends at x-coordinate 526.