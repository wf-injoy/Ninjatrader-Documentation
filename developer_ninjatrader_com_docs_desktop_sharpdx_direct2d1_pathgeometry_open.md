## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#definition)

Retrieves the geometry sink that is used to populate the path geometry with figures and segments.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371522.aspx))

## Note

Notes:

1. Because path geometries are immutable and can only be populated once, it is an error to call **Open()** on a path geometry more than once.
2. Note that the fill mode defaults to Alternate. To set the fill mode, call [SetFillMode()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_setfillmode) before the first call to [BeginFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines). Failure to do so will put the geometry sink in an error state.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#method-return-value)

A [SharpDX.Direct2D1.GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink) which contains the address of a reference to the geometry sink that is used to populate the path geometry with figures and segments.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#syntax)

`<pathgeometry>.Open()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#parameters)

This method does not accept any parameters.

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#definition)

Retrieves the geometry sink that is used to populate the path geometry with figures and segments.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd371522.aspx))

## Note

Notes:

1. Because path geometries are immutable and can only be populated once, it is an error to call **Open()** on a path geometry more than once.
2. Note that the fill mode defaults to Alternate. To set the fill mode, call [SetFillMode()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_setfillmode) before the first call to [BeginFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addlines). Failure to do so will put the geometry sink in an error state.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#method-return-value)

A [SharpDX.Direct2D1.GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink) which contains the address of a reference to the geometry sink that is used to populate the path geometry with figures and segments.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#syntax)

`<pathgeometry>.Open()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open\#parameters)

This method does not accept any parameters.