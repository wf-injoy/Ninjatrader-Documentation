## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#definition)

Paints an area with a radial gradient.

(See also **unmanaged API documentation**)

## Note

1. The **RadialGradientBrush** is similar to the **LinearGradientBrush** in that they both map a collection of gradient stops to a gradient. However, the linear gradient has a start and an end point to define the gradient vector, while the radial gradient uses an ellipse and a gradient origin to define its gradient behavior. To define the position and size of the ellipse, use the **Center**, **RadiusX**, and **RadiusY** properties to specify the center, x-radius, and y-radius of the ellipse. The gradient origin is the center of the ellipse, unless a gradient offset is specified by using the **GradientOriginOffset** method.
2. The brush maps the gradient stop position 0.0f of the gradient origin, and the position 1.0f is mapped to the ellipse boundary. When the gradient origin is within the ellipse, the contents of the ellipse enclose the entire **0, 1** range of the brush gradient stops. If the gradient origin is outside the bounds of the ellipse, the brush still works, but its gradient is not well-defined.
3. The start point and end point are described in the brush space and are mapped to the **render target** when the brush is used. Note the starting and ending coordinates are absolute, not relative to the render target size. A value of (0, 0) maps to the upper-left corner of the render target, while a value of (1, 1) maps just one pixel diagonally away from (0, 0). If there is a nonidentity brush transform or render target transform, the brush ellipse and gradient origin are also transformed.
4. It is possible to specify an ellipse that does not completely fill the area being painted. When this occurs, the **ExtendMode** and setting (specified by the brush **GradientStopCollection**) determines how the remaining area is painted.
5. A **RadialGradientBrush** may be used only with the **render target** that created it or with the compatible targets for that render target.
6. A **RadialGradientBrush** is a device-dependent resource: your application should create radial gradient brushes after it initializes the render target with which the brushes will be used, and recreate the brushes whenever the render target needs recreated. Please see the **MSDN Direct2D Resources Overview** for more information.
7. For convenience, Direct2D provides the **RadialGradientBrushProperties** function for creating a new **RadialGradientBrush**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#syntax)

`class SolidColorBrush`

{% callout type="note %}

Tips:

1. For NinjaScript Development purposes, you can use the **NinjaTrader.Gui.DxExtensions.ToDxBrush()** helper method to convert a **System.Windows.Media.LinearGradientBrush** to a **SharpDX.Direct2D1.LinearGradientBrush**.
2. General information on Direct2D brushes can be found on the **MSDN Direct2D Brushes Overview**.

## Note

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#constructors)

| Constructor | Description |
| --- | --- |
| `new RadialGradientBrush(RenderTarget renderTarget RadialGradientBrushProperties radialGradientBrushProperties GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, BrushProperties brushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, Nullable<BrushProperties> brushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| **Center** | Retrieves or sets the center of the gradient ellipse. |
| **Dispose()** | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from **SharpDX.DisposeBase**.) |
| **IsDisposed** | Gets a value indicating whether this instance is disposed. (Inherited from **SharpDX.DisposeBase**.) |
| **GradientOriginOffset** | Retrieves or sets the offset of the gradient origin relative to the gradient ellipse's center. |
| **GradientStopCollection** | Retrieves the **GradientStopCollection** associated with this radial gradient brush object. |
| **Opacity** | Gets or sets the degree of opacity of this brush. (Inherited from **Brush**.) |
| **RadiusX** | Retrieves or sets the x-radius of the gradient ellipse. |
| **RadiusY** | Retrieves or sets the y-radius of the gradient ellipse. |
| **Transform** | Gets or sets the transform applied to this brush. (Inherited from **Brush**.) |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#definition)

Paints an area with a radial gradient.

(See also **unmanaged API documentation**)

## Note

1. The **RadialGradientBrush** is similar to the **LinearGradientBrush** in that they both map a collection of gradient stops to a gradient. However, the linear gradient has a start and an end point to define the gradient vector, while the radial gradient uses an ellipse and a gradient origin to define its gradient behavior. To define the position and size of the ellipse, use the **Center**, **RadiusX**, and **RadiusY** properties to specify the center, x-radius, and y-radius of the ellipse. The gradient origin is the center of the ellipse, unless a gradient offset is specified by using the **GradientOriginOffset** method.
2. The brush maps the gradient stop position 0.0f of the gradient origin, and the position 1.0f is mapped to the ellipse boundary. When the gradient origin is within the ellipse, the contents of the ellipse enclose the entire **0, 1** range of the brush gradient stops. If the gradient origin is outside the bounds of the ellipse, the brush still works, but its gradient is not well-defined.
3. The start point and end point are described in the brush space and are mapped to the **render target** when the brush is used. Note the starting and ending coordinates are absolute, not relative to the render target size. A value of (0, 0) maps to the upper-left corner of the render target, while a value of (1, 1) maps just one pixel diagonally away from (0, 0). If there is a nonidentity brush transform or render target transform, the brush ellipse and gradient origin are also transformed.
4. It is possible to specify an ellipse that does not completely fill the area being painted. When this occurs, the **ExtendMode** and setting (specified by the brush **GradientStopCollection**) determines how the remaining area is painted.
5. A **RadialGradientBrush** may be used only with the **render target** that created it or with the compatible targets for that render target.
6. A **RadialGradientBrush** is a device-dependent resource: your application should create radial gradient brushes after it initializes the render target with which the brushes will be used, and recreate the brushes whenever the render target needs recreated. Please see the **MSDN Direct2D Resources Overview** for more information.
7. For convenience, Direct2D provides the **RadialGradientBrushProperties** function for creating a new **RadialGradientBrush**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#syntax)

`class SolidColorBrush`

{% callout type="note %}

Tips:

1. For NinjaScript Development purposes, you can use the **NinjaTrader.Gui.DxExtensions.ToDxBrush()** helper method to convert a **System.Windows.Media.LinearGradientBrush** to a **SharpDX.Direct2D1.LinearGradientBrush**.
2. General information on Direct2D brushes can be found on the **MSDN Direct2D Brushes Overview**.

## Note

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#constructors)

| Constructor | Description |
| --- | --- |
| `new RadialGradientBrush(RenderTarget renderTarget RadialGradientBrushProperties radialGradientBrushProperties GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, BrushProperties brushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |
| `new RadialGradientBrush(RenderTarget renderTarget, RadialGradientBrushProperties radialGradientBrushProperties, Nullable<BrushProperties> brushProperties, GradientStopCollection gradientStopCollection)` | Creates a **RadialGradientBrush** that contains the specified gradient stops and has the specified transform and base opacity. |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| **Center** | Retrieves or sets the center of the gradient ellipse. |
| **Dispose()** | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from **SharpDX.DisposeBase**.) |
| **IsDisposed** | Gets a value indicating whether this instance is disposed. (Inherited from **SharpDX.DisposeBase**.) |
| **GradientOriginOffset** | Retrieves or sets the offset of the gradient origin relative to the gradient ellipse's center. |
| **GradientStopCollection** | Retrieves the **GradientStopCollection** associated with this radial gradient brush object. |
| **Opacity** | Gets or sets the degree of opacity of this brush. (Inherited from **Brush**.) |
| **RadiusX** | Retrieves or sets the x-radius of the gradient ellipse. |
| **RadiusY** | Retrieves or sets the y-radius of the gradient ellipse. |
| **Transform** | Gets or sets the transform applied to this brush. (Inherited from **Brush**.) |