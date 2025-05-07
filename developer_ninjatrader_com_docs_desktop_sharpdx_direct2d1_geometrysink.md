## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#definition)

Describes a geometric path that can contain lines, arcs, cubic Bezier curves, and quadratic Bezier curves.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316592.aspx))

## [Notes](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#notes)

## Note

1. To create a GeometrySink, describe a **PathGeometry** and retrieve the object using the **PathGeometry.Open()** method.
2. A geometry sink consists of one or more figures. Each figure is made up of one or more line, curve, or arc segments. To create a figure, call the **BeginFigure** method, specify the figure's start point, and then use its Add methods (such as **AddLine**) to add segments. When you are finished adding segments, call the **EndFigure** method. You can repeat this sequence to create additional figures. When you are finished creating figures, call the **Close** method.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#syntax)

`interface GeometrySink`

## [Methods](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#methods)

| Method | Description |
| --- | --- |
| **AddArc()** | Adds a single arc to the path geometry. |
| **AddLine()** | Creates a line segment between the current point and the specified end point and adds it to the geometry sink. |
| **AddLines()** | Creates a sequence of lines using the specified points and adds them to the geometry sink. |
| **BeginFigure()** | Starts a new figure at the specified point. |
| **Close()** | Closes the geometry sink, indicates whether it is in an error state, and resets the sink's error state. |
| **Dispose()** | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from **SharpDX.DisposeBase**.) |
| **EndFigure()** | Ends the current figure; optionally, closes it. |
| **SetFillMode()** | Specifies the method used to determine which points are inside the geometry described by this geometry sink and which points are outside. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#definition)

Describes a geometric path that can contain lines, arcs, cubic Bezier curves, and quadratic Bezier curves.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316592.aspx))

## [Notes](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#notes)

## Note

1. To create a GeometrySink, describe a **PathGeometry** and retrieve the object using the **PathGeometry.Open()** method.
2. A geometry sink consists of one or more figures. Each figure is made up of one or more line, curve, or arc segments. To create a figure, call the **BeginFigure** method, specify the figure's start point, and then use its Add methods (such as **AddLine**) to add segments. When you are finished adding segments, call the **EndFigure** method. You can repeat this sequence to create additional figures. When you are finished creating figures, call the **Close** method.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#syntax)

`interface GeometrySink`

## [Methods](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink\#methods)

| Method | Description |
| --- | --- |
| **AddArc()** | Adds a single arc to the path geometry. |
| **AddLine()** | Creates a line segment between the current point and the specified end point and adds it to the geometry sink. |
| **AddLines()** | Creates a sequence of lines using the specified points and adds them to the geometry sink. |
| **BeginFigure()** | Starts a new figure at the specified point. |
| **Close()** | Closes the geometry sink, indicates whether it is in an error state, and resets the sink's error state. |
| **Dispose()** | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from **SharpDX.DisposeBase**.) |
| **EndFigure()** | Ends the current figure; optionally, closes it. |
| **SetFillMode()** | Specifies the method used to determine which points are inside the geometry described by this geometry sink and which points are outside. |