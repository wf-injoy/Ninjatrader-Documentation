## [Definition](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#definition)

Measures the value of the **bar width** set for the primary Bars object on the chart.

## Note

This property value is not stated in pixels. To obtain the pixel-width of bars on the chart, use **GetBarPaintWidth()** instead.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#property-value)

A **double** representing the value of the bar width.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#syntax)

`<chartcontrol>.BarWidth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    double barWidth = chartControl.BarWidth;

    // Prints the width of bars on the chart
    Print(barWidth);
}

```

Based on the image below, BarWidth reveals that the bars on the chart are 4.02 pixels wide.

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#definition)

Measures the value of the **bar width** set for the primary Bars object on the chart.

## Note

This property value is not stated in pixels. To obtain the pixel-width of bars on the chart, use **GetBarPaintWidth()** instead.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#property-value)

A **double** representing the value of the bar width.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#syntax)

`<chartcontrol>.BarWidth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    double barWidth = chartControl.BarWidth;

    // Prints the width of bars on the chart
    Print(barWidth);
}

```

Based on the image below, BarWidth reveals that the bars on the chart are 4.02 pixels wide.