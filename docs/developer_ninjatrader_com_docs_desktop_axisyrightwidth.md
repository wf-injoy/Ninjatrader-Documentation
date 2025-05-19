## [Definition](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#definition)

Measures the distance (in pixels) between the y-axis and the right edge of a chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#property-value)

A double representing the number of pixels separating the y-axis and the right edge of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#syntax)

`<chartcontrol>.AxisYRightWidth`

## [Example](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels between the y-axis and the right edge of the chart
     double rightWidth = chartControl.AxisYRightWidth;
     Print(rightWidth);
}

```

Based on the image below, AxisYRightWidth reveals that the space between the y-axis and the right edge of the chart is 53 pixels on this chart.

## Note

When there are no right-justified data series on a chart, AxisYRightWidth will return 0, as there will be no space between the y-axis and the right edge.

## [Definition](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#definition)

Measures the distance (in pixels) between the y-axis and the right edge of a chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#property-value)

A double representing the number of pixels separating the y-axis and the right edge of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#syntax)

`<chartcontrol>.AxisYRightWidth`

## [Example](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels between the y-axis and the right edge of the chart
     double rightWidth = chartControl.AxisYRightWidth;
     Print(rightWidth);
}

```

Based on the image below, AxisYRightWidth reveals that the space between the y-axis and the right edge of the chart is 53 pixels on this chart.

## Note

When there are no right-justified data series on a chart, AxisYRightWidth will return 0, as there will be no space between the y-axis and the right edge.