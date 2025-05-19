## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#definition)

Represents a complex shape that may be composed of arcs, curves, and lines.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371512.aspx))

## Note

- A PathGeometry object enables you to describe a geometric path. To describe a PathGeometry object's path, use the object's **Open** method to retrieve an **GeometrySink**. Use the sink to populate the path geometry with figures and segments.
- PathGeometry objects are device-independent resources created by Factory. In general, you should create geometries once and retain them for the life of the application, or until they need to be modified. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#syntax)

`class PathGeometry`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#constructors)

| Constructor | Description |
| --- | --- |
| new **PathGeometry**( **Factory** factory) | Creates an empty PathGeometry. |

| Tips |
| --- |
| 1. For NinjaScript development purposes, when creating a **PathGeometry** object you should use the **NinjaTrader.Core.Globals.D2DFactory** property. | 2. General information Direct2D Path Geometries can be found on the [MSDN Path Geometries Overview](https://msdn.microsoft.com/en-us/library/ee264309(v=vs.85).aspx). |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [FigureCount](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_figurecount) | Retrieves the number of figures in the path geometry. | [FillContainsPoint()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_fillcontainspoint) | Indicates whether the area filled by the geometry would contain the specified point given the specified flattening tolerance. | [GetBounds()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_getbounds) | Retrieves the bounds of the geometry. | [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [Open()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open) | Retrieves the geometry sink that is used to populate the path geometry with figures and segments. | [SegmentCount](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_segmentcount) | Retrieves the number of segments in the path geometry. | [StrokeContainsPoint()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint) | Determines whether the geometry's stroke contains the specified point given the specified stroke thickness, style, and transform. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#definition)

Represents a complex shape that may be composed of arcs, curves, and lines.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371512.aspx))

## Note

- A PathGeometry object enables you to describe a geometric path. To describe a PathGeometry object's path, use the object's **Open** method to retrieve an **GeometrySink**. Use the sink to populate the path geometry with figures and segments.
- PathGeometry objects are device-independent resources created by Factory. In general, you should create geometries once and retain them for the life of the application, or until they need to be modified. Please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx) for more information.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#syntax)

`class PathGeometry`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#constructors)

| Constructor | Description |
| --- | --- |
| new **PathGeometry**( **Factory** factory) | Creates an empty PathGeometry. |

| Tips |
| --- |
| 1. For NinjaScript development purposes, when creating a **PathGeometry** object you should use the **NinjaTrader.Core.Globals.D2DFactory** property. | 2. General information Direct2D Path Geometries can be found on the [MSDN Path Geometries Overview](https://msdn.microsoft.com/en-us/library/ee264309(v=vs.85).aspx). |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [FigureCount](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_figurecount) | Retrieves the number of figures in the path geometry. | [FillContainsPoint()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_fillcontainspoint) | Indicates whether the area filled by the geometry would contain the specified point given the specified flattening tolerance. | [GetBounds()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_getbounds) | Retrieves the bounds of the geometry. | [IsDisposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) | [Open()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open) | Retrieves the geometry sink that is used to populate the path geometry with figures and segments. | [SegmentCount](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_segmentcount) | Retrieves the number of segments in the path geometry. | [StrokeContainsPoint()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint) | Determines whether the geometry's stroke contains the specified point given the specified stroke thickness, style, and transform. |