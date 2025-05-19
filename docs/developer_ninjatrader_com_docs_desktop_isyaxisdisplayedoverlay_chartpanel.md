## [Definition](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#definition)

Indicates any objects configured in the panel are using the Overlay scale justification.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#property-value)

A bool indicating any objects use the Overlay scale justification.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#syntax)

`ChartPanel.IsYAxisDisplayedOverlay`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#examples)

## Note

Based on the image below, **IsYAxisDisplayedOverlay** is set to True, since the SMA indicator is using the Overlay scale justification.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);

    // Trigger an alert when the Overlay scale justification is used
    if (ChartPanel.IsYAxisDisplayedOverlay)
        Alert("overlayAlert", Priority.Low, "It is not recommended to use 'Overlay' with this indicator", "", 300, Brushes.Yellow, Brushes.Black);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#definition)

Indicates any objects configured in the panel are using the Overlay scale justification.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#property-value)

A bool indicating any objects use the Overlay scale justification.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#syntax)

`ChartPanel.IsYAxisDisplayedOverlay`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay_chartpanel\#examples)

## Note

Based on the image below, **IsYAxisDisplayedOverlay** is set to True, since the SMA indicator is using the Overlay scale justification.

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);

    // Trigger an alert when the Overlay scale justification is used
    if (ChartPanel.IsYAxisDisplayedOverlay)
        Alert("overlayAlert", Priority.Low, "It is not recommended to use 'Overlay' with this indicator", "", 300, Brushes.Yellow, Brushes.Black);
}

```