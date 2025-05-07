## [Definition](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#definition)

Converts a y-axis pixel coordinate from application pixels to device pixels.

## Note

For more information concerning the differences between application pixels and device pixels, please see the [Working with Pixel Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_pixel_coordinates).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#method-return-value)

An int representing a y-coordinate value in terms of device pixels.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#syntax)

`ChartingExtensions.ConvertToVerticalPixels(this double x, PresentationSource target)`

`double.ConvertToVerticalPixels(PresentationSource target)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#parameters)

| x | target |
| The vertical double coordinates in application pixels to convert | The [PresenationSource](https://msdn.microsoft.com/en-us/library/system.windows.presentationsource(v=vs.110).aspx) representing the display surface used for the conversion. Note: For Charts, see [ChartControl.PresentationSource](https://developer.ninjatrader.com/docs/desktop/presentationsource). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#examples)

```jsx-150469391 csharp
int devicePixelY;

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Obtain the device-pixel coordinate corresponding to an application-pixel Y value of 500
    devicePixelY = ChartingExtensions.ConvertToVerticalPixels(500, ChartControl.PresentationSource);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#definition)

Converts a y-axis pixel coordinate from application pixels to device pixels.

## Note

For more information concerning the differences between application pixels and device pixels, please see the [Working with Pixel Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_pixel_coordinates).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#method-return-value)

An int representing a y-coordinate value in terms of device pixels.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#syntax)

`ChartingExtensions.ConvertToVerticalPixels(this double x, PresentationSource target)`

`double.ConvertToVerticalPixels(PresentationSource target)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#parameters)

| x | target |
| The vertical double coordinates in application pixels to convert | The [PresenationSource](https://msdn.microsoft.com/en-us/library/system.windows.presentationsource(v=vs.110).aspx) representing the display surface used for the conversion. Note: For Charts, see [ChartControl.PresentationSource](https://developer.ninjatrader.com/docs/desktop/presentationsource). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels\#examples)

```jsx-150469391 csharp
int devicePixelY;

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Obtain the device-pixel coordinate corresponding to an application-pixel Y value of 500
    devicePixelY = ChartingExtensions.ConvertToVerticalPixels(500, ChartControl.PresentationSource);
}

```