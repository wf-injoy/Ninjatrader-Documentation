## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#definition)

Determines whether the geometry's stroke contains the specified point given the specified stroke thickness, style, and transform.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316742.aspx))

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#method-return-value)

A bool value set to true if the geometry's stroke contains the specified point; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#syntax)

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth)`

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth, StrokeStyle strokeStyle)`

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth, StrokeStyle strokeStyle, Matrix3x2 transform)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#parameters)

| Parameter | Description |
| --- | --- |
| point | The **SharpDX.Vector2** point to test for containment. |
| strokeStyle | The **SharpDX.Direct2D1.StrokeStyle** style of stroke to apply. |
| strokeWidth | The thickness of the stroke to apply. |
| transform | The **SharpDX.Matrix3x2** transform to apply to the stroked geometry. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#definition)

Determines whether the geometry's stroke contains the specified point given the specified stroke thickness, style, and transform.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316742.aspx))

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#method-return-value)

A bool value set to true if the geometry's stroke contains the specified point; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#syntax)

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth)`

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth, StrokeStyle strokeStyle)`

`<pathgeometry>.StrokeContainsPoint(Vector2 point, float strokeWidth, StrokeStyle strokeStyle, Matrix3x2 transform)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_strokecontainspoint\#parameters)

| Parameter | Description |
| --- | --- |
| point | The **SharpDX.Vector2** point to test for containment. |
| strokeStyle | The **SharpDX.Direct2D1.StrokeStyle** style of stroke to apply. |
| strokeWidth | The thickness of the stroke to apply. |
| transform | The **SharpDX.Matrix3x2** transform to apply to the stroked geometry. |