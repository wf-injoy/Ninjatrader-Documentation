## [Definition](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#definition)

Indicates if the drawing tool is currently set as a Global Drawing object. Global draw objects display on any chart which matches the parent chart's underlying instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#property-value)

A bool value which returns true if the drawing tool is currently attached as a global drawing object; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#syntax)

`IsGlobalDrawingTool`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   // do not interact if attached to global chart
   if (IsGlobalDrawingTool)
     return;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#definition)

Indicates if the drawing tool is currently set as a Global Drawing object. Global draw objects display on any chart which matches the parent chart's underlying instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#property-value)

A bool value which returns true if the drawing tool is currently attached as a global drawing object; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#syntax)

`IsGlobalDrawingTool`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   // do not interact if attached to global chart
   if (IsGlobalDrawingTool)
     return;
}

```