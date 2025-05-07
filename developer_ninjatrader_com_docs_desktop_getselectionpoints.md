## [Definition](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#definition)

Returns the chart object's data points where the user can interact. These points are used to visually indicate that the chart object is selected and allow the user to manipulate the chart object. This method is only called when **IsSelected** is set to true.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#method-return-value)

A collection of [Points](https://developer.ninjatrader.com/docs/desktop/points) representing the x- and y-coordinates of the chart object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#syntax)

You must override the method using the following syntax:

`public override Point[] GetSelectionPoints(ChartControl chartControl, ChartScale chartScale){ }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#examples)

```jsx-150469391 csharp
public override Point[] GetSelectionPoints(ChartControl chartControl, ChartScale chartScale)
{
    ChartPanel chartPanel = chartControl.ChartPanels[chartScale.PanelIndex];
    // get the anchor point to be displayed on the drawing tool
    Point anchorPoint = Anchor.GetPoint(chartControl, chartPanel, chartScale, false);
    return new[] { anchorPoint };
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#definition)

Returns the chart object's data points where the user can interact. These points are used to visually indicate that the chart object is selected and allow the user to manipulate the chart object. This method is only called when **IsSelected** is set to true.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#method-return-value)

A collection of [Points](https://developer.ninjatrader.com/docs/desktop/points) representing the x- and y-coordinates of the chart object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#syntax)

You must override the method using the following syntax:

`public override Point[] GetSelectionPoints(ChartControl chartControl, ChartScale chartScale){ }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getselectionpoints\#examples)

```jsx-150469391 csharp
public override Point[] GetSelectionPoints(ChartControl chartControl, ChartScale chartScale)
{
    ChartPanel chartPanel = chartControl.ChartPanels[chartScale.PanelIndex];
    // get the anchor point to be displayed on the drawing tool
    Point anchorPoint = Anchor.GetPoint(chartControl, chartPanel, chartScale, false);
    return new[] { anchorPoint };
}

```