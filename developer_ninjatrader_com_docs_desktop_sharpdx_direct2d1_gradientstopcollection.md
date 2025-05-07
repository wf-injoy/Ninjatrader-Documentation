## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#definition)

Describes an elliptical arc between two points.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368065.aspx))

## Note

A gradient stop collection is a device-dependent resource: your application should create gradient stop collections after it initializes the render target with which the gradient stop collection will be used, and recreate the gradient stop collection whenever the render target needs recreated. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#syntax)

`class GradientStopCollection`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#constructors)

| Constructor | Description |
| --- | --- |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops) | Creates an GradientStopCollection from the specified gradient stops, a Gamma.StandardRgb, and ExtendMode.Clamp |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, ExtendMode extendMode) | Creates an GradientStopCollection from the specified gradient stops, color Gamma.StandardRgb, and extend mode |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, Gamma colorInterpolationGamma) | Creates an GradientStopCollection from the specified gradient stops, color interpolation gamma, and ExtendMode.Clamp |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, Gamma colorInterpolationGamma, ExtendMode extendMode) | Creates an GradientStopCollection from the specified gradient stops, color interpolation gamma, and extend mode |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| [**ColorInterpolationGamma**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_colorinterpolationgamma) \| Indicates the gamma space in which the gradient stops are interpolated | [**Dispose()**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) \| Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [**ExtendMode**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_extendmode) \| Indicates the behavior of the gradient outside the normalized gradient range | [**GradientStopCount**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_gradientstopcount) \| Retrieves the number of gradient stops in the collection | [**IsDisposed**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) \| Gets a value indicating whether this instance is disposed. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#definition)

Describes an elliptical arc between two points.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368065.aspx))

## Note

A gradient stop collection is a device-dependent resource: your application should create gradient stop collections after it initializes the render target with which the gradient stop collection will be used, and recreate the gradient stop collection whenever the render target needs recreated. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#syntax)

`class GradientStopCollection`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#constructors)

| Constructor | Description |
| --- | --- |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops) | Creates an GradientStopCollection from the specified gradient stops, a Gamma.StandardRgb, and ExtendMode.Clamp |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, ExtendMode extendMode) | Creates an GradientStopCollection from the specified gradient stops, color Gamma.StandardRgb, and extend mode |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, Gamma colorInterpolationGamma) | Creates an GradientStopCollection from the specified gradient stops, color interpolation gamma, and ExtendMode.Clamp |
| new GradientStopCollection(RenderTarget rendertarget, GradientStop\[\] gradientStops, Gamma colorInterpolationGamma, ExtendMode extendMode) | Creates an GradientStopCollection from the specified gradient stops, color interpolation gamma, and extend mode |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| [**ColorInterpolationGamma**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_colorinterpolationgamma) \| Indicates the gamma space in which the gradient stops are interpolated | [**Dispose()**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) \| Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [**ExtendMode**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_extendmode) \| Indicates the behavior of the gradient outside the normalized gradient range | [**GradientStopCount**](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection_gradientstopcount) \| Retrieves the number of gradient stops in the collection | [**IsDisposed**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) \| Gets a value indicating whether this instance is disposed. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |