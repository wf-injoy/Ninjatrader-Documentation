## [Definition](https://developer.ninjatrader.com/docs/desktop/presentationsource\#definition)

Provides a reference to the base window in which the chart is rendered. **PresentationSource** can be used when converting application pixels to/from device pixels via the helper methods in the [ChartingExtensions](https://developer.ninjatrader.com/docs/desktop/chartingextensions) class.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/presentationsource\#property-value)

A **PresentationSource** object representing the base window in which the chart is rendered.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/presentationsource\#syntax)

`ChartControl.PresentationSource`

## [Examples](https://developer.ninjatrader.com/docs/desktop/presentationsource\#examples)

```jsx-150469391 csharp
int devicePixelX;
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Obtain the device-pixel coordinate corresponding to an application-pixel X value of 500
   devicePixelX = ChartingExtensions.ConvertToHorizontalPixels(500, ChartControl.PresentationSource);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/presentationsource\#definition)

Provides a reference to the base window in which the chart is rendered. **PresentationSource** can be used when converting application pixels to/from device pixels via the helper methods in the [ChartingExtensions](https://developer.ninjatrader.com/docs/desktop/chartingextensions) class.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/presentationsource\#property-value)

A **PresentationSource** object representing the base window in which the chart is rendered.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/presentationsource\#syntax)

`ChartControl.PresentationSource`

## [Examples](https://developer.ninjatrader.com/docs/desktop/presentationsource\#examples)

```jsx-150469391 csharp
int devicePixelX;
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Obtain the device-pixel coordinate corresponding to an application-pixel X value of 500
   devicePixelX = ChartingExtensions.ConvertToHorizontalPixels(500, ChartControl.PresentationSource);
}

```