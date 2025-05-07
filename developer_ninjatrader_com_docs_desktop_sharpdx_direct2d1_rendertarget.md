## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#definition)

Represents an object that can receive drawing commands.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371766.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#syntax)

`class RenderTarget`

## [Tips](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#tips)

1. For NinjaScript Development purposes, [DrawingTools](https://developer.ninjatrader.com/docs/desktop/drawingtool), [ChartStyles](https://developer.ninjatrader.com/docs/desktop/chartstyletype), [Indicators](https://developer.ninjatrader.com/docs/desktop/system_indicator_methods), and [Strategies](https://developer.ninjatrader.com/docs/desktop/strategy) implement the Chart's [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) ready to be used in the OnRender() method.
2. General information on Direct2D Render Targets can be found on the [MSDN Direct2D Render Targets Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_antialiasmode) | Retrieves or sets the current antialiasing mode for nontext drawing operations. |
| [DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) | Draws the outline of the specified geometry. |
| [DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) | Draws a line between the specified points. |
| [DrawRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle) | Draws the outline of a rectangle that has the specified dimensions. |
| [DrawText()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtext) | Draws the specified text using the format information provided by an **SharpDX.DirectWrite.TextFormat** object. |
| [DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) | Draws the formatted text described by the specified **SharpDX.DirectWrite.TextLayout** object. |
| [FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) | Paints the interior of the specified ellipse. |
| [FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) | Paints the interior of the specified geometry. |
| [FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) | Paints the interior of the specified rectangle. |
| [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from **SharpDX.DisposeBase**.) |
| [Transform](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_transform) | Gets or sets the current transform of the render target. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#definition)

Represents an object that can receive drawing commands.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371766.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#syntax)

`class RenderTarget`

## [Tips](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#tips)

1. For NinjaScript Development purposes, [DrawingTools](https://developer.ninjatrader.com/docs/desktop/drawingtool), [ChartStyles](https://developer.ninjatrader.com/docs/desktop/chartstyletype), [Indicators](https://developer.ninjatrader.com/docs/desktop/system_indicator_methods), and [Strategies](https://developer.ninjatrader.com/docs/desktop/strategy) implement the Chart's [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) ready to be used in the OnRender() method.
2. General information on Direct2D Render Targets can be found on the [MSDN Direct2D Render Targets Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_antialiasmode) | Retrieves or sets the current antialiasing mode for nontext drawing operations. |
| [DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) | Draws the outline of the specified geometry. |
| [DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) | Draws a line between the specified points. |
| [DrawRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle) | Draws the outline of a rectangle that has the specified dimensions. |
| [DrawText()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtext) | Draws the specified text using the format information provided by an **SharpDX.DirectWrite.TextFormat** object. |
| [DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) | Draws the formatted text described by the specified **SharpDX.DirectWrite.TextLayout** object. |
| [FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) | Paints the interior of the specified ellipse. |
| [FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) | Paints the interior of the specified geometry. |
| [FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) | Paints the interior of the specified rectangle. |
| [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from **SharpDX.DisposeBase**.) |
| [Transform](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_transform) | Gets or sets the current transform of the render target. |