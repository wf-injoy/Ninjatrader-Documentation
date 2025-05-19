## [Definition](https://developer.ninjatrader.com/docs/desktop/chartpanels\#definition)

Holds a collection of **ChartPanel** objects containing information about the panels active on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartpanels\#property-value)

An **ObservableCollection** of **ChartPanel** objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartpanels\#syntax)

`<chartcontrol>.ChartPanels`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartpanels\#examples)

## Note

Based on the image below, there are three ChartPanel objects in the ChartPanels collection, as seen by **ChartPanels.Count** in the code above.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Print the number of panels currently displayed on the chart
   Print(String.Format("There are {0} panels on the chart", chartControl.ChartPanels.Count));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartpanels\#definition)

Holds a collection of **ChartPanel** objects containing information about the panels active on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartpanels\#property-value)

An **ObservableCollection** of **ChartPanel** objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartpanels\#syntax)

`<chartcontrol>.ChartPanels`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartpanels\#examples)

## Note

Based on the image below, there are three ChartPanel objects in the ChartPanels collection, as seen by **ChartPanels.Count** in the code above.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Print the number of panels currently displayed on the chart
   Print(String.Format("There are {0} panels on the chart", chartControl.ChartPanels.Count));
}

```