## [Definition](https://developer.ninjatrader.com/docs/desktop/drawingtool\#definition)

The **DrawingTool** object which owns a chart anchor.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawingtool\#property-value)

A **IDrawingTool** object representing the owner of the chart anchor.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawingtool\#syntax)

`<chartanchor>.DrawingTool`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawingtool\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
						Name = "SampleDrawingTool";
						MyAnchor = new ChartAnchor();
						MyAnchor.DrawingTool = this; // NinjaTrader.NinjaScript.DrawingTools.SampleDrawingTool
			}
     else if (State == State.Configure)
     {

     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawingtool\#definition)

The **DrawingTool** object which owns a chart anchor.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawingtool\#property-value)

A **IDrawingTool** object representing the owner of the chart anchor.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawingtool\#syntax)

`<chartanchor>.DrawingTool`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawingtool\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
						Name = "SampleDrawingTool";
						MyAnchor = new ChartAnchor();
						MyAnchor.DrawingTool = this; // NinjaTrader.NinjaScript.DrawingTools.SampleDrawingTool
			}
     else if (State == State.Configure)
     {

     }
}

```