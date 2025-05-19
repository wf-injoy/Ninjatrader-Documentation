## [Definition](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#definition)

Indicates the maximum Y value of objects within the chart panel, based on the current y-axis scale. The scale of the y-axis is dependent upon the values of objects in the panel which have Auto Scale enabled.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#property-value)

A **double** representing the maximum Y value in the panel's vertical scale

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#syntax)

`ChartPanel.MaxValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);

   // Print the minimum and maximum Y values for objects in the panel
   Print(String.Format("Min value: {0}, Max value: {1}", ChartPanel.MinValue, ChartPanel.MaxValue));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#definition)

Indicates the maximum Y value of objects within the chart panel, based on the current y-axis scale. The scale of the y-axis is dependent upon the values of objects in the panel which have Auto Scale enabled.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#property-value)

A **double** representing the maximum Y value in the panel's vertical scale

## [Syntax](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#syntax)

`ChartPanel.MaxValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/maxvalue_chartpanel\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);

   // Print the minimum and maximum Y values for objects in the panel
   Print(String.Format("Min value: {0}, Max value: {1}", ChartPanel.MinValue, ChartPanel.MaxValue));
}

```