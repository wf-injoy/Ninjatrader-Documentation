## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#definition)

Draws a line between the specified points.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371895.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#syntax)

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush)`

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush, float strokeWidth)`

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#parameters)

| Parameter | Description |
| --- | --- |
| **brush** | The **SharpDX.Direct2D1.Brush** brush used to paint the line's stroke. |
| **point0** | A **SharpDX.Vector2** which determines the start point of the line, in device-independent pixels. |
| **point1** | A **SharpDX.Vector2** which determines the end point of the line, in device-independent pixels. |
| **strokeStyle** | The **SharpDX.Direct2D1.StrokeStyle** to paint, or null to paint a solid line. |
| **strokeWidth** | A value greater than or equal to 0.0f that specifies the width of the stroke. If this parameter isn't specified, it defaults to 1.0f. The stroke is centered on the line. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#definition)

Draws a line between the specified points.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371895.aspx))

## Note

This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#syntax)

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush)`

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush, float strokeWidth)`

`RenderTarget.DrawLine(Vector2 point0, Vector2 point1, Brush brush, float strokeWidth, StrokeStyle strokeStyle)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline\#parameters)

| Parameter | Description |
| --- | --- |
| **brush** | The **SharpDX.Direct2D1.Brush** brush used to paint the line's stroke. |
| **point0** | A **SharpDX.Vector2** which determines the start point of the line, in device-independent pixels. |
| **point1** | A **SharpDX.Vector2** which determines the end point of the line, in device-independent pixels. |
| **strokeStyle** | The **SharpDX.Direct2D1.StrokeStyle** to paint, or null to paint a solid line. |
| **strokeWidth** | A value greater than or equal to 0.0f that specifies the width of the stroke. If this parameter isn't specified, it defaults to 1.0f. The stroke is centered on the line. |