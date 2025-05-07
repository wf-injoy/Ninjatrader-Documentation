## [Definition](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#definition)

Represents the data returned from the historical data repository in relation to the primary **ChartBars** object configured on the chart. See also [Bars](https://developer.ninjatrader.com/docs/desktop/bars).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#property-value)

A **Bars** object

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#syntax)

`ChartBars.Bars`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if(ChartBars != null && ChartBars.Bars != null)
   {
     Print("The configured bars period type represented on the chart is" + ChartBars.Bars.BarsPeriod.BarsPeriodType);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#definition)

Represents the data returned from the historical data repository in relation to the primary **ChartBars** object configured on the chart. See also [Bars](https://developer.ninjatrader.com/docs/desktop/bars).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#property-value)

A **Bars** object

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#syntax)

`ChartBars.Bars`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartbars_bars\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if(ChartBars != null && ChartBars.Bars != null)
   {
     Print("The configured bars period type represented on the chart is" + ChartBars.Bars.BarsPeriod.BarsPeriodType);
   }
}

```