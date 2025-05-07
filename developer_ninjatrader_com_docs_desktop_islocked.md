## [Definition](https://developer.ninjatrader.com/docs/desktop/islocked\#definition)

Determines if the drawing tool should be locked in place. This property can be set either manually through the UI or explicitly through code.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/islocked\#property-value)

A bool value which when true indicates that the drawing tool is locked; otherwise false. Default is set to false.

## Note

For Drawing tools which are drawn by an indicator or strategy, this property will default to true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/islocked\#syntax)

`IsLocked`

## [Examples](https://developer.ninjatrader.com/docs/desktop/islocked\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   if (IsLocked) //if the object is locked, do not attempt to move
     return;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/islocked\#definition)

Determines if the drawing tool should be locked in place. This property can be set either manually through the UI or explicitly through code.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/islocked\#property-value)

A bool value which when true indicates that the drawing tool is locked; otherwise false. Default is set to false.

## Note

For Drawing tools which are drawn by an indicator or strategy, this property will default to true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/islocked\#syntax)

`IsLocked`

## [Examples](https://developer.ninjatrader.com/docs/desktop/islocked\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   if (IsLocked) //if the object is locked, do not attempt to move
     return;
}

```