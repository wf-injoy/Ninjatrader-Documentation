## [Definition](https://developer.ninjatrader.com/docs/desktop/stroke_class\#definition)

Objects derived from the Stroke class are used to characterize how a plot is visually displayed (plotted) on a chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/stroke_class\#syntax)

`Stroke(Stroke stroke)`

`Stroke(Brush brush)`

`Stroke(Brush brush, float width)`

`Stroke(Brush brush, DashStyle dashStyleHelper, float width)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/stroke_class\#parameters)

| Parameter | Description |
| --- | --- |
| brush | The brush used to draw the plot ( [reference](http://msdn.microsoft.com/en-us/library/System.Windows.Media.Brush%28v=vs.110%29.aspx)) |
| dashStyleHelper | Possible values:<br>- DashStyleHelper.Dash<br>- DashStyleHelper.DashDot<br>- DashStyleHelper.DashDotDot<br>- DashStyleHelper.Dot<br>- DashStyleHelper.Solid |
| stroke | The [stroke](https://developer.ninjatrader.com/docs/desktop/stroke_class) object |
| width | The width of the stroke |

## [Properties](https://developer.ninjatrader.com/docs/desktop/stroke_class\#properties)

| Brush | The System.Windows.Media.Brush used to construct the stroke ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.media.brushes%28v=vs.110%29.aspx)) |
| BrushDX | A [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to actually render the stroke Note:  To avoid and resolve access violation exceptions, please see Warning and examples remarked below |
| DashStyleDX | A [SharpDX.Direct2D1.DashStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle) used to render the stroke style Note:  To avoid and resolve access violation exceptions, please see Warning and examples remarked below |
| DashStyleHelper | A dashstyle used to construct the stroke. Possible values are:<br>- DashStyleHelper.Dash<br>- DashStyleHelper.DashDot<br>- DashStyleHelper.DashDotDot<br>- DashStyleHelper.Dot<br>- DashStyleHelper.Solid |
| RenderTarget | The [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) drawing context used for the stroke. |
| StrokeStyle | A [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) |
| Width | A float representing the width in pixels |

## Warning

There may be situations where a RenderTarget has not been set, and to prevent access violation exception before accessing the BrushDX or DashStyleDX properties, you should explicitly set the RenderTarget before attempting to access that property.  Please see the example below.

## [Examples](https://developer.ninjatrader.com/docs/desktop/stroke_class\#examples)

See the [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) method for additional examples.

### Using a Stroke SharpDX Brush for Custom Rendering

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    IsOverlay = true;
    // set the Stroke default to red brush
    MyStroke = new Stroke(Brushes.Red);
  }
  else if (State == State.Configure)
  {
  }
}

public override void OnRenderTargetChanged()
{
  // Explicitly set the Stroke RenderTarget
  if (RenderTarget != null)
    MyStroke.RenderTarget = RenderTarget;
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // create two points from the top left corner
  SharpDX.Vector2 pointA = new SharpDX.Vector2(0, 0);
  // to 300 pixels offset X and Y to create a diagonal line
  SharpDX.Vector2 pointB = new SharpDX.Vector2(300, 300);

  // Draw the line using the Stroke SharpDX brush
  RenderTarget.DrawLine(pointA, pointB, MyStroke.BrushDX, MyStroke.Width, MyStroke.StrokeStyle);

}

[NinjaScriptProperty]
[Description("My Stroke")]
public Stroke MyStroke { get; set; }

```

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    IsOverlay = true;
    // set stroke default to blue brush
    MyStroke = new Stroke(Brushes.Blue);
  }
  else if (State == State.Configure)
  {
  }
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // create two points from the top left corner
  SharpDX.Vector2 pointA = new SharpDX.Vector2(0, 0);
  // to 300 pixels offset X and Y to create a diagonal line
  SharpDX.Vector2 pointB = new SharpDX.Vector2(300, 300);

  NinjaTrader.Gui.Stroke MyStroke = new Stroke(Brushes.Blue);

  // if BrushDX is null, convert the constructed brush to a DX brush
  SharpDX.Direct2D1.Brush myBrush = MyStroke.BrushDX ?? MyStroke.Brush.ToDxBrush(RenderTarget);
  RenderTarget.DrawLine(pointA, pointB, myBrush, MyStroke.Width, MyStroke.StrokeStyle);

  myBrush.Dispose();
}

[NinjaScriptProperty]
[Description("My Stroke")]
public Stroke MyStroke { get; set; }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/stroke_class\#definition)

Objects derived from the Stroke class are used to characterize how a plot is visually displayed (plotted) on a chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/stroke_class\#syntax)

`Stroke(Stroke stroke)`

`Stroke(Brush brush)`

`Stroke(Brush brush, float width)`

`Stroke(Brush brush, DashStyle dashStyleHelper, float width)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/stroke_class\#parameters)

| Parameter | Description |
| --- | --- |
| brush | The brush used to draw the plot ( [reference](http://msdn.microsoft.com/en-us/library/System.Windows.Media.Brush%28v=vs.110%29.aspx)) |
| dashStyleHelper | Possible values:<br>- DashStyleHelper.Dash<br>- DashStyleHelper.DashDot<br>- DashStyleHelper.DashDotDot<br>- DashStyleHelper.Dot<br>- DashStyleHelper.Solid |
| stroke | The [stroke](https://developer.ninjatrader.com/docs/desktop/stroke_class) object |
| width | The width of the stroke |

## [Properties](https://developer.ninjatrader.com/docs/desktop/stroke_class\#properties)

| Brush | The System.Windows.Media.Brush used to construct the stroke ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.media.brushes%28v=vs.110%29.aspx)) |
| BrushDX | A [SharpDX.Direct2D1.Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) used to actually render the stroke Note:  To avoid and resolve access violation exceptions, please see Warning and examples remarked below |
| DashStyleDX | A [SharpDX.Direct2D1.DashStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_dashstyle) used to render the stroke style Note:  To avoid and resolve access violation exceptions, please see Warning and examples remarked below |
| DashStyleHelper | A dashstyle used to construct the stroke. Possible values are:<br>- DashStyleHelper.Dash<br>- DashStyleHelper.DashDot<br>- DashStyleHelper.DashDotDot<br>- DashStyleHelper.Dot<br>- DashStyleHelper.Solid |
| RenderTarget | The [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) drawing context used for the stroke. |
| StrokeStyle | A [SharpDX.Direct2D1.StrokeStyle](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle) |
| Width | A float representing the width in pixels |

## Warning

There may be situations where a RenderTarget has not been set, and to prevent access violation exception before accessing the BrushDX or DashStyleDX properties, you should explicitly set the RenderTarget before attempting to access that property.  Please see the example below.

## [Examples](https://developer.ninjatrader.com/docs/desktop/stroke_class\#examples)

See the [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) method for additional examples.

### Using a Stroke SharpDX Brush for Custom Rendering

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    IsOverlay = true;
    // set the Stroke default to red brush
    MyStroke = new Stroke(Brushes.Red);
  }
  else if (State == State.Configure)
  {
  }
}

public override void OnRenderTargetChanged()
{
  // Explicitly set the Stroke RenderTarget
  if (RenderTarget != null)
    MyStroke.RenderTarget = RenderTarget;
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // create two points from the top left corner
  SharpDX.Vector2 pointA = new SharpDX.Vector2(0, 0);
  // to 300 pixels offset X and Y to create a diagonal line
  SharpDX.Vector2 pointB = new SharpDX.Vector2(300, 300);

  // Draw the line using the Stroke SharpDX brush
  RenderTarget.DrawLine(pointA, pointB, MyStroke.BrushDX, MyStroke.Width, MyStroke.StrokeStyle);

}

[NinjaScriptProperty]
[Description("My Stroke")]
public Stroke MyStroke { get; set; }

```

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    IsOverlay = true;
    // set stroke default to blue brush
    MyStroke = new Stroke(Brushes.Blue);
  }
  else if (State == State.Configure)
  {
  }
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // create two points from the top left corner
  SharpDX.Vector2 pointA = new SharpDX.Vector2(0, 0);
  // to 300 pixels offset X and Y to create a diagonal line
  SharpDX.Vector2 pointB = new SharpDX.Vector2(300, 300);

  NinjaTrader.Gui.Stroke MyStroke = new Stroke(Brushes.Blue);

  // if BrushDX is null, convert the constructed brush to a DX brush
  SharpDX.Direct2D1.Brush myBrush = MyStroke.BrushDX ?? MyStroke.Brush.ToDxBrush(RenderTarget);
  RenderTarget.DrawLine(pointA, pointB, myBrush, MyStroke.Width, MyStroke.StrokeStyle);

  myBrush.Dispose();
}

[NinjaScriptProperty]
[Description("My Stroke")]
public Stroke MyStroke { get; set; }

```