## [Definition](https://developer.ninjatrader.com/docs/desktop/onmousemove\#definition)

An event driven method which is called any time the mouse pointer is over the chart control and a mouse is moving.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmousemove\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmousemove\#syntax)

You must override the method in your Drawing Tool with the following syntax.

`public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)  { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmousemove\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user is moving the mouse |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmousemove\#examples)

```jsx-150469391 csharp
private ChartAnchor lastMouseMoveAnchor = new ChartAnchor();
private ChartAnchor MyAnchor;

public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
    // add any logic for when the mouse is moved here
    if (DrawingState == DrawingState.Moving)
    {
        //move the chart anchor when the drawing tool is in a moving state
        MyAnchor.MoveAnchor(lastMouseMoveAnchor, dataPoint, chartControl, chartPanel, chartScale, this);
        // dont forget to update delta point to last used!
        dataPoint.CopyDataValues(lastMouseMoveAnchor);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onmousemove\#definition)

An event driven method which is called any time the mouse pointer is over the chart control and a mouse is moving.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmousemove\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmousemove\#syntax)

You must override the method in your Drawing Tool with the following syntax.

`public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)  { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmousemove\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user is moving the mouse |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmousemove\#examples)

```jsx-150469391 csharp
private ChartAnchor lastMouseMoveAnchor = new ChartAnchor();
private ChartAnchor MyAnchor;

public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
    // add any logic for when the mouse is moved here
    if (DrawingState == DrawingState.Moving)
    {
        //move the chart anchor when the drawing tool is in a moving state
        MyAnchor.MoveAnchor(lastMouseMoveAnchor, dataPoint, chartControl, chartPanel, chartScale, this);
        // dont forget to update delta point to last used!
        dataPoint.CopyDataValues(lastMouseMoveAnchor);
    }
}

```