## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#definition)

Draws the outline of the specified geometry using the specified stroke style.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371890.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#syntax)

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush)`

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush, float strokeWidth)`

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#parameters)

| **brush** | An int which represents the method input |
| **geometry** | The [SharpDX.Direct2D1.Geometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) to draw |
| **strokeStyle** | The [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) to apply to the geometry's outline, or null to paint a solid stroke. |
| **strokeWidth** | The thickness of the geometry's stroke. The stroke is centered on the geometry's outline. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#definition)

Draws the outline of the specified geometry using the specified stroke style.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371890.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#syntax)

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush)`

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush, float strokeWidth)`

`RenderTarget.DrawGeometry(Geometry geometry, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry\#parameters)

| **brush** | An int which represents the method input |
| **geometry** | The [SharpDX.Direct2D1.Geometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) to draw |
| **strokeStyle** | The [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) to apply to the geometry's outline, or null to paint a solid stroke. |
| **strokeWidth** | The thickness of the geometry's stroke. The stroke is centered on the geometry's outline. |