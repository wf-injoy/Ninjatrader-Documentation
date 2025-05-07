## [Definition](https://developer.ninjatrader.com/docs/desktop/onmouseup\#definition)

An event driven method is called any time the mouse pointer is over the chart control and a mouse button is being released.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmouseup\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmouseup\#syntax)

You must override the method with the following syntax.

`public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmouseup\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user is releasing the mouse |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmouseup\#examples)

```jsx-150469391 csharp
public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   //when the user releases the mouse, ensure the drawing state is set to normal
   if (DrawingState == DrawingState.Editing || DrawingState == DrawingState.Moving)
     DrawingState = DrawingState.Normal;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onmouseup\#definition)

An event driven method is called any time the mouse pointer is over the chart control and a mouse button is being released.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmouseup\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmouseup\#syntax)

You must override the method with the following syntax.

`public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmouseup\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user is releasing the mouse |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmouseup\#examples)

```jsx-150469391 csharp
public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   //when the user releases the mouse, ensure the drawing state is set to normal
   if (DrawingState == DrawingState.Editing || DrawingState == DrawingState.Moving)
     DrawingState = DrawingState.Normal;
}

```