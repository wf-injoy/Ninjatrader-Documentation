## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#definition)

Draws the outline of a rectangle that has the specified dimensions and stroke style.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371902.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#syntax)

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush)`

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush, float strokeWidth)`

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#parameters)

| brush | The **SharpDX.Direct2D1.Brush** used to paint the rectangle's stroke. |
| rect | The **SharpDX.RectangleF** which determines the dimensions of the rectangle to draw, in device-independent pixels. |
| strokeStyle | The **SharpDX.Direct2D1.StrokeStyle** used to paint, or null to paint a solid stroke. |
| strokeWidth | A value greater than or equal to 0.0f that specifies the width of the rectangle's stroke. The stroke is centered on the rectangle's outline. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#definition)

Draws the outline of a rectangle that has the specified dimensions and stroke style.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371902.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#syntax)

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush)`

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush, float strokeWidth)`

`RenderTarget.DrawRectangle(RectangleF rect, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle\#parameters)

| brush | The **SharpDX.Direct2D1.Brush** used to paint the rectangle's stroke. |
| rect | The **SharpDX.RectangleF** which determines the dimensions of the rectangle to draw, in device-independent pixels. |
| strokeStyle | The **SharpDX.Direct2D1.StrokeStyle** used to paint, or null to paint a solid stroke. |
| strokeWidth | A value greater than or equal to 0.0f that specifies the width of the rectangle's stroke. The stroke is centered on the rectangle's outline. |