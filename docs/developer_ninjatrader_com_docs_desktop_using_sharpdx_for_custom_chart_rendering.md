## [Understanding the SharpDX .NET Library](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#understanding-the-sharpdx-.net-library)

NinjaTrader Chart objects (such as Indicators, Strategies, DrawingTools, ChartStyles) implement an [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) method aimed to render custom lines, shapes, and text to the chart.  To achieve the level of performance required to keep up with market data events, NinjaTrader uses a 3rd-party open-source .NET library named [SharpDX](http://sharpdx.org/).  This 3rd party library provides a C# wrapper for the powerful [Microsoft DirectX API](https://msdn.microsoft.com/en-us/library/windows/desktop/ee663274(v=vs.85).aspx) used for graphics processing and known for its hardware-accelerated performance, including 2D vector and text layout graphics used for NinjaTrader Chart Rendering.  The SharpDX/DirectX library is extensive, although NinjaTrader only uses a handful of namespaces and classes, which are documented as a guide in this reference.  In addition to this educational resource, we have also compiled a more focused collection of [SharpDX SDK Reference](https://developer.ninjatrader.com/docs/desktop/sharpdx_sdk_reference) resources to help you learn the **SharpDX** concepts used in **NinjaTrader Chart Rendering**.

## Note

Tips:

1. There are several pre-installed examples of **OnRender()** and **SharpDX** objects used in the **NinjaTrader.Custom** project.  For starters, please look at the **SampleCustomRender** indicator file

2. Although not entirely identical, the **SharpDX** wrapper is designed to resemble **System.Drawing** namespace; experienced GDI developers will be familiar with concepts discussed in this section.

3. Microsoft provides various [DirectX Programming Guides](https://msdn.microsoft.com/en-us/library/dd372337(v=vs.85).aspx) aimed to educate users with the underlying **C++ DirectX API**.  While **SharpDX (C#)** syntax is different, you may find these guides helpful for understanding **SharpDX** concepts not offered by this guide.


There are three main **SharpDX** namespaces you need to be familiar with:

| [SharpDX](https://developer.ninjatrader.com/docs/desktop/sharpdx) | Contains basic objects used by SharpDX. |
| [SharpDX.Direct2D1](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) | Contains objects used for rendering for 2D geometry, bitmaps, and text. |
| [SharpDX.DirectWrite](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) | Contains objects used for text rendering |

The rest of this page will help you navigate the fundamental concepts needed to achieve custom rendering to your charts.

## [SharpDX Vectors and Charting Coordinates](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-vectors-and-charting-coordinates)

### Understanding the SharpDX.Vector2

SharpDX Draw methods use a [SharpDX.Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) object which describes where to render a command relative to the chart panel.  These Vector2 objects can be thought as a two-dimensional point in the chart panels X and Y axis. Since the chart canvas used to draw on consists of the full panel of the chart, a vector using a value of 0 for both the X and Y coordinates would  be located in the top left corner of the chart:

```jsx-150469391 csharp
// creates a vector located at the top left corner of the chart
float x = 0;
float y = 0;
SharpDX.Vector2 myVector2 = new Vector2(x, y);

```

## Note

You can learn about [Understanding Chart Canvas Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_chart_object_coordinates) on another topic

Vector2 objects contain X and Y properties helpful to recalculate new properties based on the initial vector:

```jsx-150469391 csharp
float width = endPoint.X - startPoint.X;

float height = endPoint.Y - startPoint.Y;

```

Additionally, you can recalculate a new vector from existing vector objects:

```jsx-1168641291 csharp
SharpDX.Vector2 center = (startPoint + endPoint) / 2;

```

It is also helpful to know that Vector2 objects are similar to the [Windows Point](https://msdn.microsoft.com/en-us/library/system.windows.point(v=vs.110).aspx) structure and these two types can be used interchangeably.  Depending on the mechanism used to obtain user input or other application values, you may receive the coordinates in a Point.  For convenience, NinjaTrader provides a [DXExtension.ToVector2()](https://developer.ninjatrader.com/docs/desktop/tovector2) method used for converting between these two objects if needed:

```jsx-1168641291 csharp
SharpDX.Vector2 dxVector2 = wpfPoint.ToVector2();

```

### Calculating Chart Coordinates

If you simply used a vector with static values, your Vector2 objects would never change, and your drawing would remain fixed on a particular area of the chart (which may be desired).  However, since NinjaTrader charts are dynamic and responded to various market data updates, scroll, resize, and scale operations - you also need a way to recalculate vectors to display information dynamically. To assist in this process, NinjaTrader provides some GUI related utilities to help navigate the chart and calculate values for your custom rendering.

```jsx-150469391 csharp
// creates a vector located at the top left corner of the chart panel
startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);

// creates a vector located at the bottom right corner of the chart panel

endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);

```

Common utilities fall under 4 key components, and you can learn more about their specific functions from the help guide topics linked in the table below:

| [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) | The entire hosting grid of the Chart |
| [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) | The primary bars series configured on the Chart |
| [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) | The panel on which the calling script resides |
| [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) | The Y-Axis values of the configured ChartPanel |

## Note

For full absolute device coordinates always use ChartPanel X, Y, W, H values. ChartScale and ChartControl properties return WPF units, so they can be drastically different depending on DPI of the user's display.  You can learn about [Working with Pixel Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_pixel_coordinates) on another topic.\|

## [SharpDX Brush Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-brush-resources)

### Understanding SharpDX Brush Resources

To color or "paint" an area of the chart, you must define custom resources which describe how you wish the custom render to appear. SharpDX contains special resources modeled after the familiar [WPF Brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes). However, the two objects are different in the way they are constructed and also in how they are managed after they are used.

There are many types of SharpDX Brush Resources which all derive from the same base [Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) class.  This base object is not enough to describe how your object should be presented, so in order to use a brush for rendering purposes, you will need to determine exactly what type of brush you wish to use:

| [Direct2D1.SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush) | Paints an area with a solid color. |
| [Direct2D1.RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush) | Paints an area with a radial gradient. |
| [Direct2D1.LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush) | Paints an area with a linear gradient. |

### Describing SolidColorBrush Colors

The most common and simple brush to use is a [Direct2D1.SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush) which allows you to paint using a solid color (or with transparency). In the most basic form, SolidColorBrush can be constructed using a predefined [SharpDX.Color](https://developer.ninjatrader.com/docs/desktop/sharpdx_color)

```jsx-1168641291 csharp
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

```

You can also use a [SharpDX.Color3](https://developer.ninjatrader.com/docs/desktop/sharpdx_color3) or [SharpDX.Color4](https://developer.ninjatrader.com/docs/desktop/sharpdx_color4) structure as a way to get more customizable colors in your rendering:

```jsx-150469391 csharp
// create a 3 component color using rgb values in float notation
SharpDX.Color3 dxColor3 = new SharpDX.Color3(1.0f, 0.0f, 0.0f);

// create a 4 component color using rgb + alpha (transparency) in float notation
SharpDX.Color4 dxColor4 = new SharpDX.Color4(dxColor3, 0.5f);

// solid color brush uses a Color4 during construction
SharpDX.Direct2D1.SolidColorBrush argbColorBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, dxColor4);

```

Alternatively, you can set the "transparency" of an existing brush by accessing its [Opacity](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_opacity) property:

```jsx-1168641291 csharp
customDXBrush.Opacity = .25f;

```

## Note

Unlike their [WPF counterparts](https://developer.ninjatrader.com/docs/desktop/working_with_brushes), SharpDX brushes are thread-safe and do NOT need to be frozen.

### Converting SharpDX Brushes

SharpDX Brushes are device-dependent resources, which means they can only be used with the device (i.e., [RenderTarget](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget)) which created them.  In practice, this mean you should ONLY create your SharpDX brushes during the chart object's [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) methods.

## Warning

Failure to create device-dependent resources during the OnRender() or OnRenderTargetChanged() can lead to a host of issues including memory and application corruption which can negatively impact the stability of NinjaTrader.  Please be careful your SharpDX device-dependent resources are only created and updated during either of these two run-time methods.  Please see the **Best Practices for SharpDX Resources** section on this page for more information.

Because of this detail, a common problem you may run into is the requirement to share a SharpDX device brush resource with a WPF application brush.  For example, you may have WPF brushes defined in the UI during [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) or recalculated conditionally during [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate), but ultimately wish to use also in custom rendering routines.  For convenience, NinjaTrader provide a [DXExtension.ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) method used for converting these objects if necessary:

```jsx-150469391 csharp
areaBrushDx = areaBrush.ToDxBrush(RenderTarget);

smallAreaBrushDx = smallAreaBrush.ToDxBrush(RenderTarget);

textBrushDx = textBrush.ToDxBrush(RenderTarget);

```

## Note

If you are using a large number of brushes, and are not tied to WPF resources, you should favor creating the SharpDX Brush directly since the ToDxBrush() method can lead to performance issues if called too frequently during a single render pass.  Please see the **Best Practices for SharpDX Resources** section on this page for more information.

## [SharpDX RenderTarget](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-rendertarget)

### Understanding the RenderTarget

A [SharpDX Render Target](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget) is a general purpose object resource used for receiving and executing drawing commands.  When using a NinjaTrader chart object, a pre-constructed Chart [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) object is available for you to use and ready to receive commands.  You can think of the RenderTarget as the device context you are using to render to (i.e. the Chart Panel).  While there is nothing special you need to do to setup this resource, it is important to understand some details regarding the RenderTarget to learn how it can be used.

The RenderTarget is primarily used for executing commands such as drawing shapes or text:

```jsx-1168641291 csharp
RenderTarget.DrawLine(startPoint, endPoint, areaBrushDx)

```

It is commonly used for creating various resources such as Brushes and other SharpDX objects:

```jsx-1168641291 csharp
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

```

It can also be used to set various properties to describe how the RenderTarget should render:

```jsx-1168641291 csharp
RenderTarget.AntialiasMode   = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;

```

### Sequencing RenderTarget commands

If the sequence in which objects render is essential to your custom rendering, you will need to be mindful of the order in which you call various RenderTarget members. For example, we can draw a second line which uses a different [AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode) and the renders each line in the order the render target received its commands:

```jsx-150469391 csharp
RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.Aliased;
RenderTarget.DrawLine(startPoint, endPoint, areaBrushDx, 8);


RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;
RenderTarget.DrawLine(startPoint, endPoint, customDXBrush, 2);

```

In the above example, this order of operations would result in the second [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) to be rendered "on top" of the first RenderTarget.DrawLine(). If you instead called these two methods in reverse order, you would not see the thinner line since it would be covered up by the thicker line.

## Note

It is important to realize that RenderTarget sequencing and the [Chart Object ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) are two different concepts. The ZOrder property controls the overall layer your entire chart object appears relative to other chart objects existing on the same chart. RenderTarget sequencing only affects the order objects are rendered relative itself.  Therefore, it is not possible to sequence your chart object's RenderTarget to draw on two different ZOrders (e.g., one line above chart bars and another line below).

### Using the RenderTarget with Device Resources

Throughout the lifetime of a chart, the render target is created and destroyed several times to satisfy various user commands. As a result, any resources that are created need to be recreated and destroyed as that render target is updated.   The NinjaTrader [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) method was designed to help with this process and will be called anytime the RenderTarget has changed.  You should use this method if you have objects which are passed around from various other resources.

## Warning

Failure to create device-dependent resources during the OnRender() or OnRenderTargetChanged() can lead to a host of issues including memory and application corruption which can negatively impact the stability of NinjaTrader.  Please be careful your SharpDX device-dependent resources are only created and updated during either of these two run-time methods.  Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

## [SharpDX Lines and Shapes](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-lines-and-shapes)

### RenderTarget Draw Methods

All drawings consistent of a few basic shapes which can be called through a handful of RenderTarget commands.  "Draw..." methods create just the outline of the shape, and "Fill..." will paint the interior of the shape.

| [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [RenderTarget.DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) | Draws the outline of the specified geometry using the specified stroke style. |
| [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) | Draws a line between the specified points. |
| [RenderTarget.FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) | Paints the interior of the specified ellipse. |
| [RenderTarget.FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) | Paints the interior of the specified geometry. |
| [RenderTarget.FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) | Paints the interior of the specified rectangle. |

## Note

[AntialiasMode.PerPrimitive](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode) allows for graphics to render more sharply, but comes at a performance cost.  It is recommended to set the [RenderTarget.AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_antialiasmode) back to the default AntialiasMode.Aliased after you finish your RenderTarget Draw command.   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

### Line

The simplest shape is a Line, executed by the [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) command which just takes two [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) objects which describe where to draw the line, and (optionally) the width of the line to draw:

```jsx-150469391 csharp
// create two vectors for the line to draw

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// define the brush used in the line
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target draw line with desired values
RenderTarget.DrawLine(startPoint, endPoint, customDXBrush, 2);

// always dispose of a brush when finished

customDXBrush.Dispose();

```

### Rectangle

Using either the [RenderTarget.FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) or [RenderTarget.DrawRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle) requires a [SharpDX.RectangleF](https://developer.ninjatrader.com/docs/desktop/sharpdx_rectanglef) structure, constructed using four values to represent the location (x, y) and size (width, height) of the rectangle to draw.

```jsx-150469391 csharp
// create two vectors to position the rectangle

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// calculate the desired width and heigh of the rectangle
float width = endPoint.X - startPoint.X;
float height = endPoint.Y - startPoint.Y;

// define the brush used in the rectangle

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// construct the rectangleF struct to describe the with position and size the drawing
SharpDX.RectangleF rect = new SharpDX.RectangleF(startPoint.X, startPoint.Y, width, height);


// execute the render target fill rectangle with desired values
RenderTarget.FillRectangle(rect, customDXBrush);

// always dispose of a brush when finished
customDXBrush.Dispose();

```

### Ellipse

Similar to the Rectangle, you can draw an Ellipse (or circle) using either the [RenderTarget.FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) or [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) methods using a [SharpDX Direct2D1 Ellipse](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_ellipse) struct.  For this structure, you will need to use a [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) object to determine the Center position of the ellipse, a RadiusX, and a RadiusY which determines the size of the ellipse:

```jsx-150469391 csharp
// create two vectors to position the ellipse

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// calculate the center point of the ellipse from start/end points

SharpDX.Vector2 centerPoint = (startPoint + endPoint) / 2;

// set the radius of the ellipse
float radiusX = 50;
float radiusY = 50;

// construct the rectangleF struct to describe the position and size the drawing

SharpDX.Direct2D1.Ellipse ellipse = new SharpDX.Direct2D1.Ellipse(centerPoint, radiusX, radiusY);

// define the brush used in the rectangle

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target fill ellipse with desired values
RenderTarget.FillEllipse(ellipse, customDXBrush);

// always dispose of a brush when finished

customDXBrush.Dispose();

```

### Geometry

For more complicated shapes, you can use the [RenderTarget.FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) or [RenderTarget.DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) methods using a [Direct2D1.PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) object, which is ultimately defined by a [Direct2D1.GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink) interface.

## Warning

Any SharpDX PathGeometry object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you!   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

To describe a PathGeometry object's path, use the object's [PathGeometry.Open()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open) method to retrieve an GeometrySink.  Then, use the GeometrySink to populate the geometry with figures and segments.  To create a figure, call the [GeometrySink.BeginFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_beginfigure) method, specify the figure's start point, and then use its Add methods (such as [GeometrySink.AddLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addline)) to add segments.  When you are finished adding segments, call the [GeometrySink.EndFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_endfigure) method. You can repeat this sequence to create additional figures. When you are finished creating figures, call the [GeometrySink.Close()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_close) method.

```jsx-150469391 csharp
// create three vectors to position the geometry

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);
SharpDX.Vector2 centerPoint = (startPoint + endPoint) / 2;

// create the PathGeometry used by the RenderTarget Fill/Draw method
SharpDX.Direct2D1.PathGeometry trianglePathGeometry   = new SharpDX.Direct2D1.PathGeometry(Core.Globals.D2DFactory);

// retrieve the GeometrySink used to describe the PathGeometry
SharpDX.Direct2D1.GeometrySink geometrySink   = trianglePathGeometry.Open();

// create the points used to define the GeometrySink
SharpDX.Vector2 beginPoint = new SharpDX.Vector2(centerPoint.X, startPoint.Y);

// Create a figure using the beginPoint
geometrySink.BeginFigure(beginPoint, SharpDX.Direct2D1.FigureBegin.Filled);


// add lines to the figure
SharpDX.Vector2 line1 = new SharpDX.Vector2(endPoint.X, centerPoint.Y);
geometrySink.AddLine(line1);
SharpDX.Vector2 line2 = new SharpDX.Vector2(centerPoint.X, endPoint.Y);
geometrySink.AddLine(line2);

// end and close figure when finished
geometrySink.EndFigure(SharpDX.Direct2D1.FigureEnd.Closed);
geometrySink.Close();


// define the brush used in the geometry

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// execute the render target fill geometry with desired values
RenderTarget.FillGeometry(trianglePathGeometry, customDXBrush);

// always dispose of a PathGeometry when finished

## trianglePathGeometry.Dispose();

// always dispose of a brush when finished

## customDXBrush.Dispose();

```

## Note

Tip: or more examples of using Shapes for custom rendering, many of the DrawingTools included in the NinjaTrader.Custom project use these types of SharpDX objects and methods extensively.

## [SharpDX Text Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-text-rendering)

### Using SharpDX for rendering Text

Up until this point, we have been using the [SharpDX.Direct2D1](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) namespace to render shapes.  When dealing with text, there is a separate [SharpDX.DirectWrite](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) namespace which works along with the Direct2D1 objects.

There are two principle objects used for text rendering:  A TextFormat object which sets the style of the text, and a TextLayout object used to construct complex texts with various settings and provides metrics for measuring the shape the formatted text.

Each one of these objects has their own RenderTarget methods: [RenderTarget.DrawText()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtext) for simple TextFormat objects and [RenderTarget.DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) for more advanced layouts.  Both methods accept a TextFormat object; DrawTextLayout is more complicated but has better performance since it reuses the same text layout which does not need to be recalculated.

## Note

Both the TextFormat and TextLayout objects require a DirectWrite factory during construction.  For convenience, you can simply use the pre-built NinjaTrader(.Core.Globals.DirectWriteFactory)\[directwritefactory\] property.

### Formatting Text

The TextFormat object determines the font size, style and family, among other properties.

## Warning

Any SharpDX TextFormat object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you!  Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 12);

```

Once the text formatting has been described, you can use this object to immediately start rendering text in the DrawText() method.  This approach also requires a [SharpDX.RectangleF](https://developer.ninjatrader.com/docs/desktop/sharpdx_rectanglef) to help determine the size and position the text renders on the chart.

```jsx-150469391 csharp
// define the point for the text to render

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);


// construct the text format with desired font family and size
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 36);


// construct the rectangleF struct to describe the position and size the text
SharpDX.RectangleF rectangleF = new SharpDX.RectangleF(startPoint.X, startPoint.Y, ChartPanel.W, ChartPanel.H);

// define the brush used for the text

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target text command with desired values
RenderTarget.DrawText("I am some text", textFormat, rectangleF, customDXBrush);


// always dispose of textFormat when finished
textFormat.Dispose();

// always dipose of brush when finished
customDXBrush.Dispose();

```

### Converting Text

One common approach to text formatting is to use the same formats as existing chart objects.  This provides familiar text format matching other objects which exist on the chart. To accomplish this, you can simply use the ChartControl NinjaTrader(.Gui.SimpleFont)\[simplefont\] object and convert to SharpDX using the [ToDirectWriteTextFormat()](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat) method.

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextFormat textFormat = ChartControl.Properties.LabelFont.ToDirectWriteTextFormat();

```

### Text Layouts

The TextLayout object works in combination with the TextFormat object by extending its functionality and providing an interface more powerful than a simple Rectangle, enabling you to position, measure, or clip the text to a surrounding shape.

When constructing the TextLayout object, you will pass in the exact text as a string you wish to render, along with the desired TextFormat.  This gives you the ability to measure the text string after it has been formatted.  During construction, you also have an opportunity to specify the maximum height and width of the TextLayout.  For example, we can set the text layout to bound to height and width chart panel:

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(Core.Globals.DirectWriteFactory, "I am also some text", textFormat, ChartPanel.W, ChartPanel.H);

```

After the text has its format and layout,  you can use the [RenderTarget.DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) method to specify the exact location as a [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2), as well as the [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to draw the text.

```jsx-1168641291 csharp
RenderTarget.DrawTextLayout(startPoint, textLayout, customDXBrush);

```

### Measuring Text Layouts

Working with an existing TextLayout object, you can use its [TextLayout.Metrics](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics) object to retrieve metadata related to the size of the formatted text.   This is helpful if you are unsure of the size of the text before it is rendered.  For example, you may wish to draw a rectangle around the formatted text calculated width and height.  Using the approach below, the rectangle will dynamically resize to fit the text values used:

```jsx-150469391 csharp
// define the point for the text to render

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X + 20, ChartPanel.Y + 20);


// construct the text format with desired font family and size
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 36);


// construct the text layout with desired text, text format, max width and height
SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(Core.Globals.DirectWriteFactory, "I am also some text", textFormat, ChartPanel.W, ChartPanel.H);


// create a rectangle which will automatically resize to the width/height of the textLayout
SharpDX.RectangleF rectangleF = new SharpDX.RectangleF(startPoint.X, startPoint.Y, textLayout.Metrics.Width, textLayout.Metrics.Height);

// define the brush used for the text and rectangle
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// execute the render target draw rectangle with desired values
RenderTarget.DrawRectangle(rectangleF, customDXBrush);

// execute the render target text layout command with desired values
RenderTarget.DrawTextLayout(startPoint, textLayout, customDXBrush);


// always dispose of textLayout, textFormat, or brush when finished
textLayout.Dispose();
textFormat.Dispose();
customDXBrush.Dispose();

```

## Note

The TextLayout.Metrics height and width properties return the text pixel height, including the line spacing of the font.  Due to the nature of most font families, there will be an amount of line spacing above and below the text.  You can use the [TextLayout.GetLineMetrics()](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_getlinemetrics) method to help calculate the distance from the top of the text line to its baseline.

## [SharpDX Stroke Style](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-stroke-style)

### Using the StrokeStyle Object

When rendering SharpDX Lines and Shapes, you can optionally configure a [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) allowing you to utilize several pre-made [dash styles](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle), or even create a custom dash pattern.

## Note

Unlike other SharpDX objects such as brushes, the StrokeStyle is a device-independent resource.  This means you only need to create the object once throughout the lifetime of the script.  However, the StrokeStyle needs to be disposed of when the script is terminated.  The Creating a Custom DashStyle example below shows how to use a stroke style from the beginning to end of the lifetime of your script.   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

For convenience, SharpDX provides the [StrokeStyleProperties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyleproperties) struct for creating new a StrokeStyle:

```jsx-150469391 csharp
// create a stroke style property using a pre-configured "DashDot" dash style
SharpDX.Direct2D1.StrokeStyleProperties dxStrokeStyleProperties = new SharpDX.Direct2D1.StrokeStyleProperties
{
  DashStyle = SharpDX.Direct2D1.DashStyle.DashDot,
};

```

Once you have your desired stroke style properties, you can create a new stroke style object.

## Warning

Any SharpDX StrokeStyle object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you! Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

```jsx-1168641291 csharp
SharpDX.Direct2D1.StrokeStyle dxStrokeStyle = new SharpDX.Direct2D1.StrokeStyle(NinjaTrader.Core.Globals.D2DFactory, dxStrokeStyleProperties);

```

## Note

Tip:  The SharpDX.Direct2D1.StrokeStyle require a Direct2D1 factory during construction.  For convenience, you can simply use the pre-built NinjaTrader(.Core.Globals.D2DFactory)\[d2dfactory\] property. The [DirectD2D](https://developer.ninjatrader.com/docs/desktop/d2dfactory) factory should only be instantiated and access from [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged), as access outside those methods could cause performance issues.\|

And then use that object with the RenderTarget.DrawLine() method:

```jsx-1168641291 csharp
RenderTarget.DrawLine(startPoint, endPoint, dxBrush, width, dxStrokeStyle);

```

### Creating a Custom DashStyle

By setting the [StrokeStyle.DashStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle) property to "Custom", you can further refine the appearance of a SharpDX rendered line or shape by describing the length and space between the lines. Creating a custom DashStyle is not only useful for using RenderTarget methods, but also can be used for customizing the appearance of standard [NinjaScript Plots](https://developer.ninjatrader.com/docs/desktop/addplot).

The code example creates a single StrokeStyle object using custom dash style properties.  The example then uses those the custom stroke style object with user defined dashes for overriding the default NinjaTrader plot appearances, and using the same stroke style in a [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) command.

```jsx-150469391 csharp
// a SharpDX.Direct2D1.StrokeStyle is device independent
// it only needs to be setup once throughout the lifetime of your script
private SharpDX.Direct2D1.StrokeStyle dxStrokeStyle;

protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Custom StrokeStyle";

    AddPlot(Brushes.Blue, "Custom StrokeStyle");
  }
  else if (State == State.Configure)
  {
    // create a custom stroke style when configured
    SharpDX.Direct2D1.StrokeStyleProperties dxStrokeStyleProperties = new SharpDX.Direct2D1.StrokeStyleProperties
    {
        // set the dash style to "Custom" define the dash pattern
        DashStyle = SharpDX.Direct2D1.DashStyle.Custom,

        // set further custom/optional StrokeStyle appearances
        DashCap = CapStyle.Round,
        EndCap   = CapStyle.Flat,
        StartCap = CapStyle.Square,
        LineJoin = LineJoin.Miter,

        // offset in the dash sequence
        DashOffset = 10.0f,
    };

    // define the an array of floating-point values
    float[] dashes = { 1.0f, 2.0f, 2.0f, 3.0f, 2.0f, 2.0f };

    // create the stroke style using the custom properties and dash array
    dxStrokeStyle = new SharpDX.Direct2D1.StrokeStyle(NinjaTrader.Core.Globals.D2DFactory,
            dxStrokeStyleProperties, dashes);
  }
  else if (State == State.Terminated)
  {
    // make sure to dispose of stroke style when finished
    if (dxStrokeStyle != null)
    {
        if (!dxStrokeStyle.IsDisposed)
          dxStrokeStyle.Dispose();
    }
  }
}

protected override void OnBarUpdate()
{
  Value[0] = Close[0];
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // override the appearance of the default plot style
  Plots[0].StrokeStyle = dxStrokeStyle;
  base.OnRender(chartControl, chartScale);

  // use the custom dash style in a RenderTarget.DrawLine() commands
  using ( SharpDX.Direct2D1.SolidColorBrush dxBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue))
  {
    RenderTarget.DrawLine(new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y), new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H), dxBrush, 2, dxStrokeStyle);
  }
}

```

## [Best Practices for SharpDX Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#best-practices-for-sharpdx-resources)

### Understanding Device-dependent vs Device-independent resources

Direct2D has several types of resources which may be mapped to the different hardware devices:

- Device-independent resources are on the CPU

- Device-dependent resources are on the GPU


When device-dependent resources are created, system resources are dedicated to that object.  Resources which are device-dependent are associated with a particular RenderTarget device and are only available on that device.  Therefore, objects which were created using a RenderTarget can only be used by that device.  As the RenderTarget updates, objects which were previously created will no longer be compatible and can lead to errors.  You can use the NinjaTrader [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) method to detect when the render target has updated and gives you an opportunity to recreate resources.

Device-dependent resources

The following objects are associated with a specific RenderTarget.  They must be created and dispose of any time the RenderTarget is updated:

- [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush)

- [GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink)

- [GradientStopCollection](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection)

- [LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush)

- [RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)

- [SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush)


### Device-independent resources

The following objects are NOT associated with a specific device.  They can be created once and last for the lifetime of your script, or until they need to be modified:

- [PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry)

- [StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle)

- [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat)

- [TextLayout](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout)


## Note

For more technical information on device resources, please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx)

### SharpDX DisposeBase

Although most C# objects stored in memory are handled by the operating system, there are a few SharpDX resources which are not managed.  It is important to take care of these resources during the lifetime of your script as there is no guarantee that NinjaTrader will be able to dispose of these unmanaged references for you.

The following commonly used objects implement from the [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase) and should be disposed any time they are created:

- [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush)

- [GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink)

- [GradientStopCollection](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection)

- [LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush)

- [PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry)

- [RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)

- [SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush)

- [StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle)

- [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat)

- [TextLayout](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout)


## Warning

The list above is NOT exhaustive and there are other less common SharpDX objects that could implement DisposeBase. Failure to clean up these resources WILL result in NinjaTrader using more memory than necessary and may expose potential "memory leaks" coming from your script.  If you experience unusual amounts of memory being utilized over time, an unmanaged SharpDX resource is often times the culprit.

Since there is no guarantee that NinjaTrader will release objects from memory when your script is terminated, it is best to protect these resources from issues and call [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) as soon as possible.  This commonly involves calling Dispose() at the end of [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender),or during [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) when dealing with device- dependent resources such as brush. Device-independent resources can be created once and then retained for the life of your application.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // 1 - setup your resource
  SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue
  // 2 - use your resource
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
  // 3- dispose of your resource
  customDXBrush.Dispose()
}

```

## Note

If your resource is setup (i.e., uses the "new" keyword) during OnRender() or OnRenderTargetChange(), calling .Dispose() during [State.Terminated](https://developer.ninjatrader.com/docs/desktop/state) will ONLY dispose of the very last reference in memory and is NOT sufficient to completely manage all instances created during the lifetime of your script.  You should be diligent in calling Dispose() throughout the lifetime of the script.

You can also consider implementing the [using Statement (C# Reference)](https://msdn.microsoft.com/en-us/library/yh598w02.aspx) which will implicitly call Dispose() for you when you are done:

```jsx-150469391 csharp
// customDXBrush implicitly calls Dispose() after this block executes

using (SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue))
{
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
}

```

Critical:  Attempting to use an object which has already been disposed can lead to memory corruption that NinjaTrader may not be able to recover.  Attempts to use an object in this manner can result in an error similar to: Error on calling 'OnRender' method on bar 0: Attempted to read or write protected memory. This is often an indication that other memory is corrupt.

You can check to see if can object has been disposed of by using the [DisposeBase.IsDiposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) property:

```jsx-150469391 csharp
SharpDX.Direct2D1.Brush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// checks the object is not disposed of before using
if(!customDXBrush.IsDisposed)
{
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
  customDXBrush.Dispose();
}

```

You should also favor managing these resources yourself, which means methods which accept a SharpDX DisposeBase object as an argument should be created before they are passed into the method and disposed of after they are used.  For example, the code below should be avoided:

**Practice to avoid**

```jsx-150469391 csharp

// do NOT convert an object as it is passed to an argument.

// You may have no chance to Dispose of the object!

// Finalizer is not guaranteed to release of these resources
RenderTarget.DrawLine(startPoint, endPoint, Brushes.AliceBlue.ToDxBrush(RenderTarget));

MyCustomMethod(Brushes.AliceBlue.ToDxBrush(RenderTarget));

```

Instead, you should manage these objects yourself:

```jsx-150469391 csharp
// Do create and store this reference yourself so you can control when it is released (Y)
SharpDX.Direct2D1.Brush customDXBrush = WPFBrush.ToDxBrush(RenderTarget);

RenderTarget.DrawLine(startPoint, endPoint, customDXBrush));

MyCustomMethod(customDXBrush);

```

### Other Best Practices

If possible, you should avoid using the [ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) method if it is not necessary.  It is relatively harmless to use this approach for a few brushes, but can introduce performance issues if used too liberally.

**Practice to avoid**

```jsx-150469391 csharp
// do NOT convert from WPF brushes unnecessarily

SharpDX.Direct2D1.Brush dxBrush1 = System.Windows.Media.Brushes.Blue.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush2 = System.Windows.Media.Brushes.Red.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush3 = System.Windows.Media.Brushes.Green.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush4 = System.Windows.Media.Brushes.Purple.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush5 = System.Windows.Media.Brushes.Orange.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush6 = System.Windows.Media.Brushes.Yellow.ToDxBrush(RenderTarget);

```

**Best practice**

```jsx-150469391 csharp
// Do create SharpDX Brushes directly if you have a large amount of brushes
SharpDX.Direct2D1.Brush dxBrush1 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue);
SharpDX.Direct2D1.Brush dxBrush2 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Red);
SharpDX.Direct2D1.Brush dxBrush3 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Green);
SharpDX.Direct2D1.Brush dxBrush4 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Purple);
SharpDX.Direct2D1.Brush dxBrush5 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Orange);
SharpDX.Direct2D1.Brush dxBrush6 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Yellow);

```

Rendering with anti-aliasing disabled can be used to render a higher qualify shapes but comes as a performance impact.  You should make sure to set this render target property back to its default when you are finished with a render routine.

```jsx-150469391 csharp
// AntialiasMode.PerPrimitive is more resource intensive

// store the old reference before setting the desired value
SharpDX.Direct2D1.AntialiasMode oldAntialiasMode = RenderTarget.AntialiasMode;
RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;

// execute your render routines

// and then set back to initial AntialiasMode when finished
RenderTarget.AntialiasMode = oldAntialiasMode;

```

## [Understanding the SharpDX .NET Library](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#understanding-the-sharpdx-.net-library)

NinjaTrader Chart objects (such as Indicators, Strategies, DrawingTools, ChartStyles) implement an [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) method aimed to render custom lines, shapes, and text to the chart.  To achieve the level of performance required to keep up with market data events, NinjaTrader uses a 3rd-party open-source .NET library named [SharpDX](http://sharpdx.org/).  This 3rd party library provides a C# wrapper for the powerful [Microsoft DirectX API](https://msdn.microsoft.com/en-us/library/windows/desktop/ee663274(v=vs.85).aspx) used for graphics processing and known for its hardware-accelerated performance, including 2D vector and text layout graphics used for NinjaTrader Chart Rendering.  The SharpDX/DirectX library is extensive, although NinjaTrader only uses a handful of namespaces and classes, which are documented as a guide in this reference.  In addition to this educational resource, we have also compiled a more focused collection of [SharpDX SDK Reference](https://developer.ninjatrader.com/docs/desktop/sharpdx_sdk_reference) resources to help you learn the **SharpDX** concepts used in **NinjaTrader Chart Rendering**.

## Note

Tips:

1. There are several pre-installed examples of **OnRender()** and **SharpDX** objects used in the **NinjaTrader.Custom** project.  For starters, please look at the **SampleCustomRender** indicator file

2. Although not entirely identical, the **SharpDX** wrapper is designed to resemble **System.Drawing** namespace; experienced GDI developers will be familiar with concepts discussed in this section.

3. Microsoft provides various [DirectX Programming Guides](https://msdn.microsoft.com/en-us/library/dd372337(v=vs.85).aspx) aimed to educate users with the underlying **C++ DirectX API**.  While **SharpDX (C#)** syntax is different, you may find these guides helpful for understanding **SharpDX** concepts not offered by this guide.


There are three main **SharpDX** namespaces you need to be familiar with:

| [SharpDX](https://developer.ninjatrader.com/docs/desktop/sharpdx) | Contains basic objects used by SharpDX. |
| [SharpDX.Direct2D1](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) | Contains objects used for rendering for 2D geometry, bitmaps, and text. |
| [SharpDX.DirectWrite](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) | Contains objects used for text rendering |

The rest of this page will help you navigate the fundamental concepts needed to achieve custom rendering to your charts.

## [SharpDX Vectors and Charting Coordinates](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-vectors-and-charting-coordinates)

### Understanding the SharpDX.Vector2

SharpDX Draw methods use a [SharpDX.Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) object which describes where to render a command relative to the chart panel.  These Vector2 objects can be thought as a two-dimensional point in the chart panels X and Y axis. Since the chart canvas used to draw on consists of the full panel of the chart, a vector using a value of 0 for both the X and Y coordinates would  be located in the top left corner of the chart:

```jsx-150469391 csharp
// creates a vector located at the top left corner of the chart
float x = 0;
float y = 0;
SharpDX.Vector2 myVector2 = new Vector2(x, y);

```

## Note

You can learn about [Understanding Chart Canvas Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_chart_object_coordinates) on another topic

Vector2 objects contain X and Y properties helpful to recalculate new properties based on the initial vector:

```jsx-150469391 csharp
float width = endPoint.X - startPoint.X;

float height = endPoint.Y - startPoint.Y;

```

Additionally, you can recalculate a new vector from existing vector objects:

```jsx-1168641291 csharp
SharpDX.Vector2 center = (startPoint + endPoint) / 2;

```

It is also helpful to know that Vector2 objects are similar to the [Windows Point](https://msdn.microsoft.com/en-us/library/system.windows.point(v=vs.110).aspx) structure and these two types can be used interchangeably.  Depending on the mechanism used to obtain user input or other application values, you may receive the coordinates in a Point.  For convenience, NinjaTrader provides a [DXExtension.ToVector2()](https://developer.ninjatrader.com/docs/desktop/tovector2) method used for converting between these two objects if needed:

```jsx-1168641291 csharp
SharpDX.Vector2 dxVector2 = wpfPoint.ToVector2();

```

### Calculating Chart Coordinates

If you simply used a vector with static values, your Vector2 objects would never change, and your drawing would remain fixed on a particular area of the chart (which may be desired).  However, since NinjaTrader charts are dynamic and responded to various market data updates, scroll, resize, and scale operations - you also need a way to recalculate vectors to display information dynamically. To assist in this process, NinjaTrader provides some GUI related utilities to help navigate the chart and calculate values for your custom rendering.

```jsx-150469391 csharp
// creates a vector located at the top left corner of the chart panel
startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);

// creates a vector located at the bottom right corner of the chart panel

endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);

```

Common utilities fall under 4 key components, and you can learn more about their specific functions from the help guide topics linked in the table below:

| [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) | The entire hosting grid of the Chart |
| [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) | The primary bars series configured on the Chart |
| [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) | The panel on which the calling script resides |
| [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) | The Y-Axis values of the configured ChartPanel |

## Note

For full absolute device coordinates always use ChartPanel X, Y, W, H values. ChartScale and ChartControl properties return WPF units, so they can be drastically different depending on DPI of the user's display.  You can learn about [Working with Pixel Coordinates](https://developer.ninjatrader.com/docs/desktop/working_with_pixel_coordinates) on another topic.\|

## [SharpDX Brush Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-brush-resources)

### Understanding SharpDX Brush Resources

To color or "paint" an area of the chart, you must define custom resources which describe how you wish the custom render to appear. SharpDX contains special resources modeled after the familiar [WPF Brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes). However, the two objects are different in the way they are constructed and also in how they are managed after they are used.

There are many types of SharpDX Brush Resources which all derive from the same base [Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) class.  This base object is not enough to describe how your object should be presented, so in order to use a brush for rendering purposes, you will need to determine exactly what type of brush you wish to use:

| [Direct2D1.SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush) | Paints an area with a solid color. |
| [Direct2D1.RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush) | Paints an area with a radial gradient. |
| [Direct2D1.LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush) | Paints an area with a linear gradient. |

### Describing SolidColorBrush Colors

The most common and simple brush to use is a [Direct2D1.SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush) which allows you to paint using a solid color (or with transparency). In the most basic form, SolidColorBrush can be constructed using a predefined [SharpDX.Color](https://developer.ninjatrader.com/docs/desktop/sharpdx_color)

```jsx-1168641291 csharp
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

```

You can also use a [SharpDX.Color3](https://developer.ninjatrader.com/docs/desktop/sharpdx_color3) or [SharpDX.Color4](https://developer.ninjatrader.com/docs/desktop/sharpdx_color4) structure as a way to get more customizable colors in your rendering:

```jsx-150469391 csharp
// create a 3 component color using rgb values in float notation
SharpDX.Color3 dxColor3 = new SharpDX.Color3(1.0f, 0.0f, 0.0f);

// create a 4 component color using rgb + alpha (transparency) in float notation
SharpDX.Color4 dxColor4 = new SharpDX.Color4(dxColor3, 0.5f);

// solid color brush uses a Color4 during construction
SharpDX.Direct2D1.SolidColorBrush argbColorBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, dxColor4);

```

Alternatively, you can set the "transparency" of an existing brush by accessing its [Opacity](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush_opacity) property:

```jsx-1168641291 csharp
customDXBrush.Opacity = .25f;

```

## Note

Unlike their [WPF counterparts](https://developer.ninjatrader.com/docs/desktop/working_with_brushes), SharpDX brushes are thread-safe and do NOT need to be frozen.

### Converting SharpDX Brushes

SharpDX Brushes are device-dependent resources, which means they can only be used with the device (i.e., [RenderTarget](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget)) which created them.  In practice, this mean you should ONLY create your SharpDX brushes during the chart object's [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) methods.

## Warning

Failure to create device-dependent resources during the OnRender() or OnRenderTargetChanged() can lead to a host of issues including memory and application corruption which can negatively impact the stability of NinjaTrader.  Please be careful your SharpDX device-dependent resources are only created and updated during either of these two run-time methods.  Please see the **Best Practices for SharpDX Resources** section on this page for more information.

Because of this detail, a common problem you may run into is the requirement to share a SharpDX device brush resource with a WPF application brush.  For example, you may have WPF brushes defined in the UI during [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) or recalculated conditionally during [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate), but ultimately wish to use also in custom rendering routines.  For convenience, NinjaTrader provide a [DXExtension.ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) method used for converting these objects if necessary:

```jsx-150469391 csharp
areaBrushDx = areaBrush.ToDxBrush(RenderTarget);

smallAreaBrushDx = smallAreaBrush.ToDxBrush(RenderTarget);

textBrushDx = textBrush.ToDxBrush(RenderTarget);

```

## Note

If you are using a large number of brushes, and are not tied to WPF resources, you should favor creating the SharpDX Brush directly since the ToDxBrush() method can lead to performance issues if called too frequently during a single render pass.  Please see the **Best Practices for SharpDX Resources** section on this page for more information.

## [SharpDX RenderTarget](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-rendertarget)

### Understanding the RenderTarget

A [SharpDX Render Target](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget) is a general purpose object resource used for receiving and executing drawing commands.  When using a NinjaTrader chart object, a pre-constructed Chart [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) object is available for you to use and ready to receive commands.  You can think of the RenderTarget as the device context you are using to render to (i.e. the Chart Panel).  While there is nothing special you need to do to setup this resource, it is important to understand some details regarding the RenderTarget to learn how it can be used.

The RenderTarget is primarily used for executing commands such as drawing shapes or text:

```jsx-1168641291 csharp
RenderTarget.DrawLine(startPoint, endPoint, areaBrushDx)

```

It is commonly used for creating various resources such as Brushes and other SharpDX objects:

```jsx-1168641291 csharp
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

```

It can also be used to set various properties to describe how the RenderTarget should render:

```jsx-1168641291 csharp
RenderTarget.AntialiasMode   = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;

```

### Sequencing RenderTarget commands

If the sequence in which objects render is essential to your custom rendering, you will need to be mindful of the order in which you call various RenderTarget members. For example, we can draw a second line which uses a different [AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode) and the renders each line in the order the render target received its commands:

```jsx-150469391 csharp
RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.Aliased;
RenderTarget.DrawLine(startPoint, endPoint, areaBrushDx, 8);


RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;
RenderTarget.DrawLine(startPoint, endPoint, customDXBrush, 2);

```

In the above example, this order of operations would result in the second [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) to be rendered "on top" of the first RenderTarget.DrawLine(). If you instead called these two methods in reverse order, you would not see the thinner line since it would be covered up by the thicker line.

## Note

It is important to realize that RenderTarget sequencing and the [Chart Object ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) are two different concepts. The ZOrder property controls the overall layer your entire chart object appears relative to other chart objects existing on the same chart. RenderTarget sequencing only affects the order objects are rendered relative itself.  Therefore, it is not possible to sequence your chart object's RenderTarget to draw on two different ZOrders (e.g., one line above chart bars and another line below).

### Using the RenderTarget with Device Resources

Throughout the lifetime of a chart, the render target is created and destroyed several times to satisfy various user commands. As a result, any resources that are created need to be recreated and destroyed as that render target is updated.   The NinjaTrader [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) method was designed to help with this process and will be called anytime the RenderTarget has changed.  You should use this method if you have objects which are passed around from various other resources.

## Warning

Failure to create device-dependent resources during the OnRender() or OnRenderTargetChanged() can lead to a host of issues including memory and application corruption which can negatively impact the stability of NinjaTrader.  Please be careful your SharpDX device-dependent resources are only created and updated during either of these two run-time methods.  Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

## [SharpDX Lines and Shapes](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-lines-and-shapes)

### RenderTarget Draw Methods

All drawings consistent of a few basic shapes which can be called through a handful of RenderTarget commands.  "Draw..." methods create just the outline of the shape, and "Fill..." will paint the interior of the shape.

| [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) | Draws the outline of the specified ellipse using the specified stroke style. |
| [RenderTarget.DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) | Draws the outline of the specified geometry using the specified stroke style. |
| [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) | Draws a line between the specified points. |
| [RenderTarget.FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) | Paints the interior of the specified ellipse. |
| [RenderTarget.FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) | Paints the interior of the specified geometry. |
| [RenderTarget.FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) | Paints the interior of the specified rectangle. |

## Note

[AntialiasMode.PerPrimitive](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode) allows for graphics to render more sharply, but comes at a performance cost.  It is recommended to set the [RenderTarget.AntialiasMode](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_antialiasmode) back to the default AntialiasMode.Aliased after you finish your RenderTarget Draw command.   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

### Line

The simplest shape is a Line, executed by the [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) command which just takes two [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) objects which describe where to draw the line, and (optionally) the width of the line to draw:

```jsx-150469391 csharp
// create two vectors for the line to draw

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// define the brush used in the line
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target draw line with desired values
RenderTarget.DrawLine(startPoint, endPoint, customDXBrush, 2);

// always dispose of a brush when finished

customDXBrush.Dispose();

```

### Rectangle

Using either the [RenderTarget.FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle) or [RenderTarget.DrawRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawrectangle) requires a [SharpDX.RectangleF](https://developer.ninjatrader.com/docs/desktop/sharpdx_rectanglef) structure, constructed using four values to represent the location (x, y) and size (width, height) of the rectangle to draw.

```jsx-150469391 csharp
// create two vectors to position the rectangle

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// calculate the desired width and heigh of the rectangle
float width = endPoint.X - startPoint.X;
float height = endPoint.Y - startPoint.Y;

// define the brush used in the rectangle

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// construct the rectangleF struct to describe the with position and size the drawing
SharpDX.RectangleF rect = new SharpDX.RectangleF(startPoint.X, startPoint.Y, width, height);


// execute the render target fill rectangle with desired values
RenderTarget.FillRectangle(rect, customDXBrush);

// always dispose of a brush when finished
customDXBrush.Dispose();

```

### Ellipse

Similar to the Rectangle, you can draw an Ellipse (or circle) using either the [RenderTarget.FillEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillellipse) or [RenderTarget.DrawEllipse()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawellipse) methods using a [SharpDX Direct2D1 Ellipse](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_ellipse) struct.  For this structure, you will need to use a [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) object to determine the Center position of the ellipse, a RadiusX, and a RadiusY which determines the size of the ellipse:

```jsx-150469391 csharp
// create two vectors to position the ellipse

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);


// calculate the center point of the ellipse from start/end points

SharpDX.Vector2 centerPoint = (startPoint + endPoint) / 2;

// set the radius of the ellipse
float radiusX = 50;
float radiusY = 50;

// construct the rectangleF struct to describe the position and size the drawing

SharpDX.Direct2D1.Ellipse ellipse = new SharpDX.Direct2D1.Ellipse(centerPoint, radiusX, radiusY);

// define the brush used in the rectangle

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target fill ellipse with desired values
RenderTarget.FillEllipse(ellipse, customDXBrush);

// always dispose of a brush when finished

customDXBrush.Dispose();

```

### Geometry

For more complicated shapes, you can use the [RenderTarget.FillGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillgeometry) or [RenderTarget.DrawGeometry()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawgeometry) methods using a [Direct2D1.PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry) object, which is ultimately defined by a [Direct2D1.GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink) interface.

## Warning

Any SharpDX PathGeometry object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you!   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

To describe a PathGeometry object's path, use the object's [PathGeometry.Open()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry_open) method to retrieve an GeometrySink.  Then, use the GeometrySink to populate the geometry with figures and segments.  To create a figure, call the [GeometrySink.BeginFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_beginfigure) method, specify the figure's start point, and then use its Add methods (such as [GeometrySink.AddLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_addline)) to add segments.  When you are finished adding segments, call the [GeometrySink.EndFigure()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_endfigure) method. You can repeat this sequence to create additional figures. When you are finished creating figures, call the [GeometrySink.Close()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink_close) method.

```jsx-150469391 csharp
// create three vectors to position the geometry

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);
SharpDX.Vector2 endPoint = new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H);
SharpDX.Vector2 centerPoint = (startPoint + endPoint) / 2;

// create the PathGeometry used by the RenderTarget Fill/Draw method
SharpDX.Direct2D1.PathGeometry trianglePathGeometry   = new SharpDX.Direct2D1.PathGeometry(Core.Globals.D2DFactory);

// retrieve the GeometrySink used to describe the PathGeometry
SharpDX.Direct2D1.GeometrySink geometrySink   = trianglePathGeometry.Open();

// create the points used to define the GeometrySink
SharpDX.Vector2 beginPoint = new SharpDX.Vector2(centerPoint.X, startPoint.Y);

// Create a figure using the beginPoint
geometrySink.BeginFigure(beginPoint, SharpDX.Direct2D1.FigureBegin.Filled);


// add lines to the figure
SharpDX.Vector2 line1 = new SharpDX.Vector2(endPoint.X, centerPoint.Y);
geometrySink.AddLine(line1);
SharpDX.Vector2 line2 = new SharpDX.Vector2(centerPoint.X, endPoint.Y);
geometrySink.AddLine(line2);

// end and close figure when finished
geometrySink.EndFigure(SharpDX.Direct2D1.FigureEnd.Closed);
geometrySink.Close();


// define the brush used in the geometry

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// execute the render target fill geometry with desired values
RenderTarget.FillGeometry(trianglePathGeometry, customDXBrush);

// always dispose of a PathGeometry when finished

## trianglePathGeometry.Dispose();

// always dispose of a brush when finished

## customDXBrush.Dispose();

```

## Note

Tip: or more examples of using Shapes for custom rendering, many of the DrawingTools included in the NinjaTrader.Custom project use these types of SharpDX objects and methods extensively.

## [SharpDX Text Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-text-rendering)

### Using SharpDX for rendering Text

Up until this point, we have been using the [SharpDX.Direct2D1](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) namespace to render shapes.  When dealing with text, there is a separate [SharpDX.DirectWrite](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) namespace which works along with the Direct2D1 objects.

There are two principle objects used for text rendering:  A TextFormat object which sets the style of the text, and a TextLayout object used to construct complex texts with various settings and provides metrics for measuring the shape the formatted text.

Each one of these objects has their own RenderTarget methods: [RenderTarget.DrawText()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtext) for simple TextFormat objects and [RenderTarget.DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) for more advanced layouts.  Both methods accept a TextFormat object; DrawTextLayout is more complicated but has better performance since it reuses the same text layout which does not need to be recalculated.

## Note

Both the TextFormat and TextLayout objects require a DirectWrite factory during construction.  For convenience, you can simply use the pre-built NinjaTrader(.Core.Globals.DirectWriteFactory)\[directwritefactory\] property.

### Formatting Text

The TextFormat object determines the font size, style and family, among other properties.

## Warning

Any SharpDX TextFormat object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you!  Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 12);

```

Once the text formatting has been described, you can use this object to immediately start rendering text in the DrawText() method.  This approach also requires a [SharpDX.RectangleF](https://developer.ninjatrader.com/docs/desktop/sharpdx_rectanglef) to help determine the size and position the text renders on the chart.

```jsx-150469391 csharp
// define the point for the text to render

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y);


// construct the text format with desired font family and size
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 36);


// construct the rectangleF struct to describe the position and size the text
SharpDX.RectangleF rectangleF = new SharpDX.RectangleF(startPoint.X, startPoint.Y, ChartPanel.W, ChartPanel.H);

// define the brush used for the text

SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// execute the render target text command with desired values
RenderTarget.DrawText("I am some text", textFormat, rectangleF, customDXBrush);


// always dispose of textFormat when finished
textFormat.Dispose();

// always dipose of brush when finished
customDXBrush.Dispose();

```

### Converting Text

One common approach to text formatting is to use the same formats as existing chart objects.  This provides familiar text format matching other objects which exist on the chart. To accomplish this, you can simply use the ChartControl NinjaTrader(.Gui.SimpleFont)\[simplefont\] object and convert to SharpDX using the [ToDirectWriteTextFormat()](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat) method.

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextFormat textFormat = ChartControl.Properties.LabelFont.ToDirectWriteTextFormat();

```

### Text Layouts

The TextLayout object works in combination with the TextFormat object by extending its functionality and providing an interface more powerful than a simple Rectangle, enabling you to position, measure, or clip the text to a surrounding shape.

When constructing the TextLayout object, you will pass in the exact text as a string you wish to render, along with the desired TextFormat.  This gives you the ability to measure the text string after it has been formatted.  During construction, you also have an opportunity to specify the maximum height and width of the TextLayout.  For example, we can set the text layout to bound to height and width chart panel:

```jsx-1168641291 csharp
SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(Core.Globals.DirectWriteFactory, "I am also some text", textFormat, ChartPanel.W, ChartPanel.H);

```

After the text has its format and layout,  you can use the [RenderTarget.DrawTextLayout()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawtextlayout) method to specify the exact location as a [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2), as well as the [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to draw the text.

```jsx-1168641291 csharp
RenderTarget.DrawTextLayout(startPoint, textLayout, customDXBrush);

```

### Measuring Text Layouts

Working with an existing TextLayout object, you can use its [TextLayout.Metrics](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics) object to retrieve metadata related to the size of the formatted text.   This is helpful if you are unsure of the size of the text before it is rendered.  For example, you may wish to draw a rectangle around the formatted text calculated width and height.  Using the approach below, the rectangle will dynamically resize to fit the text values used:

```jsx-150469391 csharp
// define the point for the text to render

SharpDX.Vector2 startPoint = new SharpDX.Vector2(ChartPanel.X + 20, ChartPanel.Y + 20);


// construct the text format with desired font family and size
SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(Core.Globals.DirectWriteFactory, "Arial", 36);


// construct the text layout with desired text, text format, max width and height
SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(Core.Globals.DirectWriteFactory, "I am also some text", textFormat, ChartPanel.W, ChartPanel.H);


// create a rectangle which will automatically resize to the width/height of the textLayout
SharpDX.RectangleF rectangleF = new SharpDX.RectangleF(startPoint.X, startPoint.Y, textLayout.Metrics.Width, textLayout.Metrics.Height);

// define the brush used for the text and rectangle
SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);

// execute the render target draw rectangle with desired values
RenderTarget.DrawRectangle(rectangleF, customDXBrush);

// execute the render target text layout command with desired values
RenderTarget.DrawTextLayout(startPoint, textLayout, customDXBrush);


// always dispose of textLayout, textFormat, or brush when finished
textLayout.Dispose();
textFormat.Dispose();
customDXBrush.Dispose();

```

## Note

The TextLayout.Metrics height and width properties return the text pixel height, including the line spacing of the font.  Due to the nature of most font families, there will be an amount of line spacing above and below the text.  You can use the [TextLayout.GetLineMetrics()](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_getlinemetrics) method to help calculate the distance from the top of the text line to its baseline.

## [SharpDX Stroke Style](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#sharpdx-stroke-style)

### Using the StrokeStyle Object

When rendering SharpDX Lines and Shapes, you can optionally configure a [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) allowing you to utilize several pre-made [dash styles](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle), or even create a custom dash pattern.

## Note

Unlike other SharpDX objects such as brushes, the StrokeStyle is a device-independent resource.  This means you only need to create the object once throughout the lifetime of the script.  However, the StrokeStyle needs to be disposed of when the script is terminated.  The Creating a Custom DashStyle example below shows how to use a stroke style from the beginning to end of the lifetime of your script.   Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

For convenience, SharpDX provides the [StrokeStyleProperties](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyleproperties) struct for creating new a StrokeStyle:

```jsx-150469391 csharp
// create a stroke style property using a pre-configured "DashDot" dash style
SharpDX.Direct2D1.StrokeStyleProperties dxStrokeStyleProperties = new SharpDX.Direct2D1.StrokeStyleProperties
{
  DashStyle = SharpDX.Direct2D1.DashStyle.DashDot,
};

```

Once you have your desired stroke style properties, you can create a new stroke style object.

## Warning

Any SharpDX StrokeStyle object used in your development must be disposed of after they have been used. NinjaTrader is NOT guaranteed to dispose of these resources for you! Please see the **\[Best Practices for SharpDX Resources\]** section on this page for more information.

```jsx-1168641291 csharp
SharpDX.Direct2D1.StrokeStyle dxStrokeStyle = new SharpDX.Direct2D1.StrokeStyle(NinjaTrader.Core.Globals.D2DFactory, dxStrokeStyleProperties);

```

## Note

Tip:  The SharpDX.Direct2D1.StrokeStyle require a Direct2D1 factory during construction.  For convenience, you can simply use the pre-built NinjaTrader(.Core.Globals.D2DFactory)\[d2dfactory\] property. The [DirectD2D](https://developer.ninjatrader.com/docs/desktop/d2dfactory) factory should only be instantiated and access from [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged), as access outside those methods could cause performance issues.\|

And then use that object with the RenderTarget.DrawLine() method:

```jsx-1168641291 csharp
RenderTarget.DrawLine(startPoint, endPoint, dxBrush, width, dxStrokeStyle);

```

### Creating a Custom DashStyle

By setting the [StrokeStyle.DashStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle) property to "Custom", you can further refine the appearance of a SharpDX rendered line or shape by describing the length and space between the lines. Creating a custom DashStyle is not only useful for using RenderTarget methods, but also can be used for customizing the appearance of standard [NinjaScript Plots](https://developer.ninjatrader.com/docs/desktop/addplot).

The code example creates a single StrokeStyle object using custom dash style properties.  The example then uses those the custom stroke style object with user defined dashes for overriding the default NinjaTrader plot appearances, and using the same stroke style in a [RenderTarget.DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline) command.

```jsx-150469391 csharp
// a SharpDX.Direct2D1.StrokeStyle is device independent
// it only needs to be setup once throughout the lifetime of your script
private SharpDX.Direct2D1.StrokeStyle dxStrokeStyle;

protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Custom StrokeStyle";

    AddPlot(Brushes.Blue, "Custom StrokeStyle");
  }
  else if (State == State.Configure)
  {
    // create a custom stroke style when configured
    SharpDX.Direct2D1.StrokeStyleProperties dxStrokeStyleProperties = new SharpDX.Direct2D1.StrokeStyleProperties
    {
        // set the dash style to "Custom" define the dash pattern
        DashStyle = SharpDX.Direct2D1.DashStyle.Custom,

        // set further custom/optional StrokeStyle appearances
        DashCap = CapStyle.Round,
        EndCap   = CapStyle.Flat,
        StartCap = CapStyle.Square,
        LineJoin = LineJoin.Miter,

        // offset in the dash sequence
        DashOffset = 10.0f,
    };

    // define the an array of floating-point values
    float[] dashes = { 1.0f, 2.0f, 2.0f, 3.0f, 2.0f, 2.0f };

    // create the stroke style using the custom properties and dash array
    dxStrokeStyle = new SharpDX.Direct2D1.StrokeStyle(NinjaTrader.Core.Globals.D2DFactory,
            dxStrokeStyleProperties, dashes);
  }
  else if (State == State.Terminated)
  {
    // make sure to dispose of stroke style when finished
    if (dxStrokeStyle != null)
    {
        if (!dxStrokeStyle.IsDisposed)
          dxStrokeStyle.Dispose();
    }
  }
}

protected override void OnBarUpdate()
{
  Value[0] = Close[0];
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // override the appearance of the default plot style
  Plots[0].StrokeStyle = dxStrokeStyle;
  base.OnRender(chartControl, chartScale);

  // use the custom dash style in a RenderTarget.DrawLine() commands
  using ( SharpDX.Direct2D1.SolidColorBrush dxBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue))
  {
    RenderTarget.DrawLine(new SharpDX.Vector2(ChartPanel.X, ChartPanel.Y), new SharpDX.Vector2(ChartPanel.X + ChartPanel.W, ChartPanel.Y + ChartPanel.H), dxBrush, 2, dxStrokeStyle);
  }
}

```

## [Best Practices for SharpDX Resources](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering\#best-practices-for-sharpdx-resources)

### Understanding Device-dependent vs Device-independent resources

Direct2D has several types of resources which may be mapped to the different hardware devices:

- Device-independent resources are on the CPU

- Device-dependent resources are on the GPU


When device-dependent resources are created, system resources are dedicated to that object.  Resources which are device-dependent are associated with a particular RenderTarget device and are only available on that device.  Therefore, objects which were created using a RenderTarget can only be used by that device.  As the RenderTarget updates, objects which were previously created will no longer be compatible and can lead to errors.  You can use the NinjaTrader [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) method to detect when the render target has updated and gives you an opportunity to recreate resources.

Device-dependent resources

The following objects are associated with a specific RenderTarget.  They must be created and dispose of any time the RenderTarget is updated:

- [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush)

- [GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink)

- [GradientStopCollection](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection)

- [LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush)

- [RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)

- [SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush)


### Device-independent resources

The following objects are NOT associated with a specific device.  They can be created once and last for the lifetime of your script, or until they need to be modified:

- [PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry)

- [StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle)

- [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat)

- [TextLayout](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout)


## Note

For more technical information on device resources, please see the [MSDN Direct2D Resources Overview](https://msdn.microsoft.com/en-us/library/dd756757(v=vs.85).aspx)

### SharpDX DisposeBase

Although most C# objects stored in memory are handled by the operating system, there are a few SharpDX resources which are not managed.  It is important to take care of these resources during the lifetime of your script as there is no guarantee that NinjaTrader will be able to dispose of these unmanaged references for you.

The following commonly used objects implement from the [SharpDX.DisposeBase](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase) and should be disposed any time they are created:

- [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush)

- [GeometrySink](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_geometrysink)

- [GradientStopCollection](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_gradientstopcollection)

- [LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush)

- [PathGeometry](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_pathgeometry)

- [RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)

- [SolidColorBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_solidcolorbrush)

- [StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle)

- [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat)

- [TextLayout](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout)


## Warning

The list above is NOT exhaustive and there are other less common SharpDX objects that could implement DisposeBase. Failure to clean up these resources WILL result in NinjaTrader using more memory than necessary and may expose potential "memory leaks" coming from your script.  If you experience unusual amounts of memory being utilized over time, an unmanaged SharpDX resource is often times the culprit.

Since there is no guarantee that NinjaTrader will release objects from memory when your script is terminated, it is best to protect these resources from issues and call [Dispose()](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) as soon as possible.  This commonly involves calling Dispose() at the end of [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender),or during [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) when dealing with device- dependent resources such as brush. Device-independent resources can be created once and then retained for the life of your application.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // 1 - setup your resource
  SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue
  // 2 - use your resource
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
  // 3- dispose of your resource
  customDXBrush.Dispose()
}

```

## Note

If your resource is setup (i.e., uses the "new" keyword) during OnRender() or OnRenderTargetChange(), calling .Dispose() during [State.Terminated](https://developer.ninjatrader.com/docs/desktop/state) will ONLY dispose of the very last reference in memory and is NOT sufficient to completely manage all instances created during the lifetime of your script.  You should be diligent in calling Dispose() throughout the lifetime of the script.

You can also consider implementing the [using Statement (C# Reference)](https://msdn.microsoft.com/en-us/library/yh598w02.aspx) which will implicitly call Dispose() for you when you are done:

```jsx-150469391 csharp
// customDXBrush implicitly calls Dispose() after this block executes

using (SharpDX.Direct2D1.SolidColorBrush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue))
{
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
}

```

Critical:  Attempting to use an object which has already been disposed can lead to memory corruption that NinjaTrader may not be able to recover.  Attempts to use an object in this manner can result in an error similar to: Error on calling 'OnRender' method on bar 0: Attempted to read or write protected memory. This is often an indication that other memory is corrupt.

You can check to see if can object has been disposed of by using the [DisposeBase.IsDiposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) property:

```jsx-150469391 csharp
SharpDX.Direct2D1.Brush customDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.DodgerBlue);


// checks the object is not disposed of before using
if(!customDXBrush.IsDisposed)
{
  RenderTarget.DrawLine(startPoint, endPoint, customDXBrush);
  customDXBrush.Dispose();
}

```

You should also favor managing these resources yourself, which means methods which accept a SharpDX DisposeBase object as an argument should be created before they are passed into the method and disposed of after they are used.  For example, the code below should be avoided:

**Practice to avoid**

```jsx-150469391 csharp

// do NOT convert an object as it is passed to an argument.

// You may have no chance to Dispose of the object!

// Finalizer is not guaranteed to release of these resources
RenderTarget.DrawLine(startPoint, endPoint, Brushes.AliceBlue.ToDxBrush(RenderTarget));

MyCustomMethod(Brushes.AliceBlue.ToDxBrush(RenderTarget));

```

Instead, you should manage these objects yourself:

```jsx-150469391 csharp
// Do create and store this reference yourself so you can control when it is released (Y)
SharpDX.Direct2D1.Brush customDXBrush = WPFBrush.ToDxBrush(RenderTarget);

RenderTarget.DrawLine(startPoint, endPoint, customDXBrush));

MyCustomMethod(customDXBrush);

```

### Other Best Practices

If possible, you should avoid using the [ToDxBrush()](https://developer.ninjatrader.com/docs/desktop/todxbrush) method if it is not necessary.  It is relatively harmless to use this approach for a few brushes, but can introduce performance issues if used too liberally.

**Practice to avoid**

```jsx-150469391 csharp
// do NOT convert from WPF brushes unnecessarily

SharpDX.Direct2D1.Brush dxBrush1 = System.Windows.Media.Brushes.Blue.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush2 = System.Windows.Media.Brushes.Red.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush3 = System.Windows.Media.Brushes.Green.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush4 = System.Windows.Media.Brushes.Purple.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush5 = System.Windows.Media.Brushes.Orange.ToDxBrush(RenderTarget);
SharpDX.Direct2D1.Brush dxBrush6 = System.Windows.Media.Brushes.Yellow.ToDxBrush(RenderTarget);

```

**Best practice**

```jsx-150469391 csharp
// Do create SharpDX Brushes directly if you have a large amount of brushes
SharpDX.Direct2D1.Brush dxBrush1 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue);
SharpDX.Direct2D1.Brush dxBrush2 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Red);
SharpDX.Direct2D1.Brush dxBrush3 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Green);
SharpDX.Direct2D1.Brush dxBrush4 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Purple);
SharpDX.Direct2D1.Brush dxBrush5 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Orange);
SharpDX.Direct2D1.Brush dxBrush6 = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Yellow);

```

Rendering with anti-aliasing disabled can be used to render a higher qualify shapes but comes as a performance impact.  You should make sure to set this render target property back to its default when you are finished with a render routine.

```jsx-150469391 csharp
// AntialiasMode.PerPrimitive is more resource intensive

// store the old reference before setting the desired value
SharpDX.Direct2D1.AntialiasMode oldAntialiasMode = RenderTarget.AntialiasMode;
RenderTarget.AntialiasMode = SharpDX.Direct2D1.AntialiasMode.PerPrimitive;

// execute your render routines

// and then set back to initial AntialiasMode when finished
RenderTarget.AntialiasMode = oldAntialiasMode;

```