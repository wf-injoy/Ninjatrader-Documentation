## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#definition)

Draws the formatted text described by the specified **SharpDX.DirectWrite.TextLayout** object.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371913.aspx))

## Note

Notes:

1. When drawing the same text repeatedly, using the **DrawTextLayout()** method is more efficient than using the **DrawText()** method because the text doesn't need to be formatted and the layout processed with each call.
2. This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#syntax)

`RenderTarget.DrawTextLayout(Vector2 origin, TextLayout textLayout, Brush defaultForegroundBrush)`

`RenderTarget.DrawTextLayout(Vector2 origin, TextLayout textLayout, Brush defaultForegroundBrush, DrawTextOptions options)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#parameters)

| Parameter | Description |
| --- | --- |
| **defaultForegroundBrush** | The **SharpDX.Direct2D1.Brush** used to paint any text in textLayout that does not already have a brush associated with it as a drawing effect (specified by the SetDrawingEffect method). |
| **options** | A **SharpDX.Direct2D1.DrawTextOptions** value that indicates whether the text should be snapped to pixel boundaries and whether the text should be clipped to the layout rectangle. The default value is None, which indicates that text should be snapped to pixel boundaries and it should not be clipped to the layout rectangle. |
| **origin** | A **SharpDX.Vector2** described in device-independent pixels, at which the upper-left corner of the text described by textLayout is drawn. |
| **textLayout** | A **SharpDX.DirectWrite.TextLayout** representing the formatted text to draw. Any drawing effects that do not inherit from Resource are ignored. If there are drawing effects that inherit from **ID2D1Resource** that are not brushes, this method fails and the render target is put in an error state. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#definition)

Draws the formatted text described by the specified **SharpDX.DirectWrite.TextLayout** object.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371913.aspx))

## Note

Notes:

1. When drawing the same text repeatedly, using the **DrawTextLayout()** method is more efficient than using the **DrawText()** method because the text doesn't need to be formatted and the layout processed with each call.
2. This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#syntax)

`RenderTarget.DrawTextLayout(Vector2 origin, TextLayout textLayout, Brush defaultForegroundBrush)`

`RenderTarget.DrawTextLayout(Vector2 origin, TextLayout textLayout, Brush defaultForegroundBrush, DrawTextOptions options)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout\#parameters)

| Parameter | Description |
| --- | --- |
| **defaultForegroundBrush** | The **SharpDX.Direct2D1.Brush** used to paint any text in textLayout that does not already have a brush associated with it as a drawing effect (specified by the SetDrawingEffect method). |
| **options** | A **SharpDX.Direct2D1.DrawTextOptions** value that indicates whether the text should be snapped to pixel boundaries and whether the text should be clipped to the layout rectangle. The default value is None, which indicates that text should be snapped to pixel boundaries and it should not be clipped to the layout rectangle. |
| **origin** | A **SharpDX.Vector2** described in device-independent pixels, at which the upper-left corner of the text described by textLayout is drawn. |
| **textLayout** | A **SharpDX.DirectWrite.TextLayout** representing the formatted text to draw. Any drawing effects that do not inherit from Resource are ignored. If there are drawing effects that inherit from **ID2D1Resource** that are not brushes, this method fails and the render target is put in an error state. |