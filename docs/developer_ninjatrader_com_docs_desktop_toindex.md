## [Definition](https://developer.ninjatrader.com/docs/desktop/toindex\#definition)

An index value representing the last bar rendered on the chart. See also [FromIndex](https://developer.ninjatrader.com/docs/desktop/fromindex).

## Note

This value is NOT the last value that exists on the **ChartBars**, but rather the last bar index that is within the viewable range of the chart canvas area. This value changes as the user interacts with the **ChartControl** time-scale (x-axis).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/toindex\#property-value)

An int representing the last bar index painted on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/toindex\#syntax)

`ChartBars.ToIndex`

## [Examples](https://developer.ninjatrader.com/docs/desktop/toindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if (ChartBars != null)
   {
     // loop through all of the viewable range of the chart
     for (int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
     {
         // print the High value for each index within the viewable range
         Print(High.GetValueAt(barIndex));
     }
   }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/toindex\#definition)

An index value representing the last bar rendered on the chart. See also [FromIndex](https://developer.ninjatrader.com/docs/desktop/fromindex).

## Note

This value is NOT the last value that exists on the **ChartBars**, but rather the last bar index that is within the viewable range of the chart canvas area. This value changes as the user interacts with the **ChartControl** time-scale (x-axis).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/toindex\#property-value)

An int representing the last bar index painted on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/toindex\#syntax)

`ChartBars.ToIndex`

## [Examples](https://developer.ninjatrader.com/docs/desktop/toindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   if (ChartBars != null)
   {
     // loop through all of the viewable range of the chart
     for (int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
     {
         // print the High value for each index within the viewable range
         Print(High.GetValueAt(barIndex));
     }
   }

```