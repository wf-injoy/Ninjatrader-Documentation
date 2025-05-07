## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#definition)

Paints the interior of the specified geometry.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371933.aspx))

## Note

1. If the **opacityBrush** parameter is not null, the alpha value of each pixel of the mapped **opacityBrush** is used to determine the resulting opacity of each corresponding pixel of the geometry. Only the alpha value of each color in the brush is used for this processing; all other color information is ignored. The alpha value specified by the brush is multiplied by the alpha value of the geometry after the geometry has been painted by brush.
2. This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#syntax)

`RenderTarget.FillGeometry(Geometry geometry, Brush brush)`

`RenderTarget.FillGeometry(Geometry geometry, Brush brush, Brush opacityBrush)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#parameters)

| **brush** | The [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to paint the geometry's interior. |
| **geometry** | The [SharpDX.Direct2D1.Geometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) to paint. |
| **opacityBrush** | The [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) opacity mask to apply to the geometry, or null for no opacity mask. For more information, see the note section above. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#definition)

Paints the interior of the specified geometry.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371933.aspx))

## Note

1. If the **opacityBrush** parameter is not null, the alpha value of each pixel of the mapped **opacityBrush** is used to determine the resulting opacity of each corresponding pixel of the geometry. Only the alpha value of each color in the brush is used for this processing; all other color information is ignored. The alpha value specified by the brush is multiplied by the alpha value of the geometry after the geometry has been painted by brush.
2. This method doesn't return an error code if it fails.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#syntax)

`RenderTarget.FillGeometry(Geometry geometry, Brush brush)`

`RenderTarget.FillGeometry(Geometry geometry, Brush brush, Brush opacityBrush)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry\#parameters)

| **brush** | The [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to paint the geometry's interior. |
| **geometry** | The [SharpDX.Direct2D1.Geometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) to paint. |
| **opacityBrush** | The [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) opacity mask to apply to the geometry, or null for no opacity mask. For more information, see the note section above. |