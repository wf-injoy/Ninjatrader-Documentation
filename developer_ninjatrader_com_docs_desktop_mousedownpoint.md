## [Definition](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#definition)

Indicates the WPF x- and y-coordinates of the mouse cursor at the most recent **OnMouseDown()** event.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#property-value)

A [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point(v=vs.110).aspx) object containing x- and y-coordinates of the mouse cursor when the left mouse button is clicked or held.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#syntax)

`<chartcontrol>.MouseDownPoint`

## [Examples](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   Point cursorPoint = chartControl.MouseDownPoint;

   // Print the x- and y-coordinates of the mouse cursor when clicked
   Print(String.Format("Mouse clicked at coordinates {0},{1}", cursorPoint.X, cursorPoint.Y));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#definition)

Indicates the WPF x- and y-coordinates of the mouse cursor at the most recent **OnMouseDown()** event.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#property-value)

A [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point(v=vs.110).aspx) object containing x- and y-coordinates of the mouse cursor when the left mouse button is clicked or held.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#syntax)

`<chartcontrol>.MouseDownPoint`

## [Examples](https://developer.ninjatrader.com/docs/desktop/mousedownpoint\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   Point cursorPoint = chartControl.MouseDownPoint;

   // Print the x- and y-coordinates of the mouse cursor when clicked
   Print(String.Format("Mouse clicked at coordinates {0},{1}", cursorPoint.X, cursorPoint.Y));
}

```