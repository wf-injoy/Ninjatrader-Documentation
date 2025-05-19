## [Definition](https://developer.ninjatrader.com/docs/desktop/width\#definition)

Indicates the overall distance (from left to right) of the chart scale.

## Note

Width does not return its value in terms of device pixels. However, using Width.ConvertToVerticalPixels or Width.ConvertToHorizontalPixels will convert the Width value to device pixels. Alternatively, RenderTarget.PixelSize.Width or ChartPanel.W will also provide the width in terms of device pixels.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/width\#property-value)

A double value representing the width of the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/width\#syntax)

`<chartScale>.Width`

## [Examples](https://developer.ninjatrader.com/docs/desktop/width\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // the width of the entire chart scale
  double   width       = chartScale.Width;
  Print("the width of the chart scale is: " + Width);
}

```

In the image below, the entire of width of the chart scale is represented by the blue line which is calculated at 450 pixels.

## [Definition](https://developer.ninjatrader.com/docs/desktop/width\#definition)

Indicates the overall distance (from left to right) of the chart scale.

## Note

Width does not return its value in terms of device pixels. However, using Width.ConvertToVerticalPixels or Width.ConvertToHorizontalPixels will convert the Width value to device pixels. Alternatively, RenderTarget.PixelSize.Width or ChartPanel.W will also provide the width in terms of device pixels.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/width\#property-value)

A double value representing the width of the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/width\#syntax)

`<chartScale>.Width`

## [Examples](https://developer.ninjatrader.com/docs/desktop/width\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // the width of the entire chart scale
  double   width       = chartScale.Width;
  Print("the width of the chart scale is: " + Width);
}

```

In the image below, the entire of width of the chart scale is represented by the blue line which is calculated at 450 pixels.