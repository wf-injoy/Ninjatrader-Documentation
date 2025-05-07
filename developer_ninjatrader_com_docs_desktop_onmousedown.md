## [Definition](https://developer.ninjatrader.com/docs/desktop/onmousedown\#definition)

An event driven method which is called any time the mouse pointer over the chart control has the mouse button pressed.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmousedown\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmousedown\#syntax)

You must override the method in your Drawing Tool with the following syntax.

`public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint) { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmousedown\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user clicked |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmousedown\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   switch (DrawingState)
   {
     case DrawingState.Building:
         dataPoint.CopyDataValues(Anchor);
         Anchor.IsEditing   = false;
         DrawingState     = DrawingState.Normal;
         IsSelected         = false;
         break;
     case DrawingState.Normal:
         // make sure they clicked near us. use GetCursor incase something has more than one point
         Point point = dataPoint.GetPoint(chartControl, chartPanel, chartScale);
         if (GetCursor(chartControl, chartPanel, chartScale, point) != null)
           DrawingState = DrawingState.Moving;
         else
           IsSelected = false;
         break;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onmousedown\#definition)

An event driven method which is called any time the mouse pointer over the chart control has the mouse button pressed.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onmousedown\#method-return-value)

This method does not return a value.

## Note

For a combined single click operation, i.e. mouse down click, move and release the dataPoint reported will always be the initial starting one.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onmousedown\#syntax)

You must override the method in your Drawing Tool with the following syntax.

`public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint) { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onmousedown\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **dataPoint** | A [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing a point where the user clicked |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onmousedown\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   switch (DrawingState)
   {
     case DrawingState.Building:
         dataPoint.CopyDataValues(Anchor);
         Anchor.IsEditing   = false;
         DrawingState     = DrawingState.Normal;
         IsSelected         = false;
         break;
     case DrawingState.Normal:
         // make sure they clicked near us. use GetCursor incase something has more than one point
         Point point = dataPoint.GetPoint(chartControl, chartPanel, chartScale);
         if (GetCursor(chartControl, chartPanel, chartScale, point) != null)
           DrawingState = DrawingState.Moving;
         else
           IsSelected = false;
         break;
   }
}

```