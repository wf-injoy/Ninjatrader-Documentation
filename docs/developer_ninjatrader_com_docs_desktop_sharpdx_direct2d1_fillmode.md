## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#definition)

Specifies how the intersecting areas of geometries or figures are combined to form the area of the composite geometry.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368110.aspx))

## Note

Notes:

- Use the FillMode enumeration when creating or modifying the fill mode of a **GeometrySink** with the **SetFillMode()** method.
- Direct2D fills the interior of a path by using one of the two fill modes specified by this enumeration: Alternate (alternate) or Winding (winding). Because the modes determine how to fill the interior of a closed shape, all shapes are treated as closed when they are filled. If there is a gap in a segment in a shape, draw an imaginary line to close it.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#syntax)

`enum FillMode`

## [Enumerators](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#enumerators)

| Enumerator | Description |
| --- | --- |
| Alternate | Determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction, and then counting the number of path segments within the given shape that the ray crosses. If this number is odd, the point is in the fill region; if even, the point is outside the fill region. |
| Winding | Determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction, and then examining the places where a segment of the shape crosses the ray. Starting with a count of zero, add one each time a segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left, as long as left and right are seen from the perspective of the ray. After counting the crossings, if the result is zero, then the point is outside the path. Otherwise, it is inside the path. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#definition)

Specifies how the intersecting areas of geometries or figures are combined to form the area of the composite geometry.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368110.aspx))

## Note

Notes:

- Use the FillMode enumeration when creating or modifying the fill mode of a **GeometrySink** with the **SetFillMode()** method.
- Direct2D fills the interior of a path by using one of the two fill modes specified by this enumeration: Alternate (alternate) or Winding (winding). Because the modes determine how to fill the interior of a closed shape, all shapes are treated as closed when they are filled. If there is a gap in a segment in a shape, draw an imaginary line to close it.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#syntax)

`enum FillMode`

## [Enumerators](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_fillmode\#enumerators)

| Enumerator | Description |
| --- | --- |
| Alternate | Determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction, and then counting the number of path segments within the given shape that the ray crosses. If this number is odd, the point is in the fill region; if even, the point is outside the fill region. |
| Winding | Determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction, and then examining the places where a segment of the shape crosses the ray. Starting with a count of zero, add one each time a segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left, as long as left and right are seen from the perspective of the ray. After counting the crossings, if the result is zero, then the point is outside the path. Otherwise, it is inside the path. |