## [Definition](https://developer.ninjatrader.com/docs/desktop/panel\#definition)

A zero-based index value that represents the **ChartPanel** where the **ChartBars** reside.

## Note

This is NOT the same as the **PanelUI** property displays on the Chart's **Data Series** menu. A **ChartBars.Panel** value of 0 represents the first panel on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/panel\#property-value)

An int indicating the panel of the **ChartBars**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/panel\#syntax)

`Bars.Panel`

## [Examples](https://developer.ninjatrader.com/docs/desktop/panel\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  Print("ChartBars reside on panel index: " + ChartBars.Panel);
  // Output:  ChartBars reside on panel index: 0
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/panel\#definition)

A zero-based index value that represents the **ChartPanel** where the **ChartBars** reside.

## Note

This is NOT the same as the **PanelUI** property displays on the Chart's **Data Series** menu. A **ChartBars.Panel** value of 0 represents the first panel on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/panel\#property-value)

An int indicating the panel of the **ChartBars**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/panel\#syntax)

`Bars.Panel`

## [Examples](https://developer.ninjatrader.com/docs/desktop/panel\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  Print("ChartBars reside on panel index: " + ChartBars.Panel);
  // Output:  ChartBars reside on panel index: 0
}

```