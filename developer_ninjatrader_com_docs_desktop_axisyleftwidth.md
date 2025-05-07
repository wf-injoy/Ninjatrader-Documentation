## [Definition](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#definition)

Measures the distance (in pixels) between the y-axis and the left edge of a chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#property-value)

A double representing the number of pixels separating the y-axis and the left edge of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#syntax)

`ChartControl.AxisYLeftWidth`

## [Example](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels between the y-axis and the left edge of the chart
     double leftWidth = chartControl.AxisYLeftWidth;
     Print(leftWidth);
}

```

Based on the image below, AxisYLeftWidth reveals that the space between the y-axis and the left edge of the chart is 53 pixels on this chart.

## Note

When there are no left-justified data series on a chart, AxisYLeftWidth will return 0, as there will be no space between the y-axis and the left margin.

## [Definition](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#definition)

Measures the distance (in pixels) between the y-axis and the left edge of a chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#property-value)

A double representing the number of pixels separating the y-axis and the left edge of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#syntax)

`ChartControl.AxisYLeftWidth`

## [Example](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels between the y-axis and the left edge of the chart
     double leftWidth = chartControl.AxisYLeftWidth;
     Print(leftWidth);
}

```

Based on the image below, AxisYLeftWidth reveals that the space between the y-axis and the left edge of the chart is 53 pixels on this chart.

## Note

When there are no left-justified data series on a chart, AxisYLeftWidth will return 0, as there will be no space between the y-axis and the left margin.