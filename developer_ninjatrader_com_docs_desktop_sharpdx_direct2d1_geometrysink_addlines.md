## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#definition)

Creates a sequence of lines using the specified points and adds them to the geometry sink.

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd316925.aspx))

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#syntax)

`<geometrysink>.AddLines(Vector2[] pointsRef)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#parameters)

| Parameter | Description |
| --- | --- |
| pointsRef | A **SharpDX.Vector2** array of one or more points that describe the lines to draw. A line is drawn from the geometry sink's current point (the end point of the last segment drawn or the location specified by **BeginFigure()** to the first point in the array. If the array contains additional points, a line is drawn from the first point to the second point in the array, from the second point to the third point, and so on. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#definition)

Creates a sequence of lines using the specified points and adds them to the geometry sink.

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd316925.aspx))

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#syntax)

`<geometrysink>.AddLines(Vector2[] pointsRef)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines\#parameters)

| Parameter | Description |
| --- | --- |
| pointsRef | A **SharpDX.Vector2** array of one or more points that describe the lines to draw. A line is drawn from the geometry sink's current point (the end point of the last segment drawn or the location specified by **BeginFigure()** to the first point in the array. If the array contains additional points, a line is drawn from the first point to the second point in the array, from the second point to the third point, and so on. |