## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#definition)

Defines an object that paints an area. Interfaces that derive from `Brush` describe how the area is painted.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371173.aspx))

## Note

Notes:

1. An **Brush** is a device-dependent resource: your application should create brushes after it initializes the render target with which the brush will be used, and recreate the brush whenever the render target needs recreated. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.
2. Brush space in Direct2D is specified differently than in XPS and Windows Presentation Foundation (WPF). In Direct2D, brush space is not relative to the object being drawn, but rather is the current coordinate system of the render target, transformed by the brush transform, if present. To paint an object as it would be painted by a WPF brush, you must translate the brush space origin to the upper-left corner of the object's bounding box, and then scale the brush space so that the base tile fills the bounding box of the object.
3. For convenience, Direct2D provides the [BrushProperties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brushproperties) function for creating new a **Brush**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#syntax)

`class Brush`

## Note

Tips:

1. For NinjaScript Development purposes, you can use the [NinjaTrader.Gui.DxExtensions.ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) helper method to convert a **System.Windows.Media.Brush** to a **SharpDX.Direct2D1.Brush**. General information on Direct2D brushes can be found on the [MSDN Direct2D Brushes Overview](https://msdn.microsoft.com/en-us/library/dd756651(v=vs.85).aspx).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [Opacity](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_opacity) | Gets or sets the degree of opacity of this brush. |
| [Transform](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_transform) | Gets or sets the transform applied to this brush. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#definition)

Defines an object that paints an area. Interfaces that derive from `Brush` describe how the area is painted.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371173.aspx))

## Note

Notes:

1. An **Brush** is a device-dependent resource: your application should create brushes after it initializes the render target with which the brush will be used, and recreate the brush whenever the render target needs recreated. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.
2. Brush space in Direct2D is specified differently than in XPS and Windows Presentation Foundation (WPF). In Direct2D, brush space is not relative to the object being drawn, but rather is the current coordinate system of the render target, transformed by the brush transform, if present. To paint an object as it would be painted by a WPF brush, you must translate the brush space origin to the upper-left corner of the object's bounding box, and then scale the brush space so that the base tile fills the bounding box of the object.
3. For convenience, Direct2D provides the [BrushProperties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brushproperties) function for creating new a **Brush**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#syntax)

`class Brush`

## Note

Tips:

1. For NinjaScript Development purposes, you can use the [NinjaTrader.Gui.DxExtensions.ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) helper method to convert a **System.Windows.Media.Brush** to a **SharpDX.Direct2D1.Brush**. General information on Direct2D brushes can be found on the [MSDN Direct2D Brushes Overview](https://msdn.microsoft.com/en-us/library/dd756651(v=vs.85).aspx).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [Opacity](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_opacity) | Gets or sets the degree of opacity of this brush. |
| [Transform](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_transform) | Gets or sets the transform applied to this brush. |