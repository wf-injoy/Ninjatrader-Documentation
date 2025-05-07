## [Definition](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#definition)

Indicates if the chart scale is viewable on the UI. If the bar series, indicator, or strategy which uses the chart scale is not in view, the chart scale **IsVisible** property will return false.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#property-value)

A **bool** value, which when true the series used to build the scale is viewable; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#syntax)

`<chartscale>.IsVisible`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // do not process render info chart scale is not visible
   if(!chartScale.IsVisible)
     return;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#definition)

Indicates if the chart scale is viewable on the UI. If the bar series, indicator, or strategy which uses the chart scale is not in view, the chart scale **IsVisible** property will return false.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#property-value)

A **bool** value, which when true the series used to build the scale is viewable; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#syntax)

`<chartscale>.IsVisible`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartscale_isvisible\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // do not process render info chart scale is not visible
   if(!chartScale.IsVisible)
     return;
}

```