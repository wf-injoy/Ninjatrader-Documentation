## [Definition](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#definition)

A hard-coded minimum bar margin value, set to 8 pixels, which can be used as a base value when creating custom Chart Styles.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#property-value)

A value representing the minimum margin applied to the left edge of bars. This value is hard-coded to 8 pixels, and it can be used as a base value when setting the bar margin in custom [Chart Styles](https://developer.ninjatrader.com/docs/desktop/chart_style).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#syntax)

`ChartControl.BarMarginLeft`

## [Example](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels maintained as a margin to the left of bars
     double barMargin = chartControl.BarMarginLeft;
     Print(barMargin);
}

```

Based on the image below, BarMarginLeft reveals that the minimum margin maintained to the left of each bar is 8 pixels on this chart.

## [Definition](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#definition)

A hard-coded minimum bar margin value, set to 8 pixels, which can be used as a base value when creating custom Chart Styles.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#property-value)

A value representing the minimum margin applied to the left edge of bars. This value is hard-coded to 8 pixels, and it can be used as a base value when setting the bar margin in custom [Chart Styles](https://developer.ninjatrader.com/docs/desktop/chart_style).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#syntax)

`ChartControl.BarMarginLeft`

## [Example](https://developer.ninjatrader.com/docs/desktop/barmarginleft\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
     // Print the number of pixels maintained as a margin to the left of bars
     double barMargin = chartControl.BarMarginLeft;
     Print(barMargin);
}

```

Based on the image below, BarMarginLeft reveals that the minimum margin maintained to the left of each bar is 8 pixels on this chart.