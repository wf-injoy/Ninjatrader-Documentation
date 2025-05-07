## [Definition](https://developer.ninjatrader.com/docs/desktop/fromindex\#definition)

An index value representing the first bar rendered on the chart. See also **ToIndex**.

## Note

This value is NOT the first value that exists on the **ChartBars**, but rather the first bar index that is within the viewable range of the chart canvas area. This value changes as the user interacts with the **ChartControl** time-scale (x-axis).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/fromindex\#property-value)

An int representing the first bar index painted on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/fromindex\#syntax)

`ChartBars.FromIndex`

## [Examples](https://developer.ninjatrader.com/docs/desktop/fromindex\#examples)

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
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/fromindex\#definition)

An index value representing the first bar rendered on the chart. See also **ToIndex**.

## Note

This value is NOT the first value that exists on the **ChartBars**, but rather the first bar index that is within the viewable range of the chart canvas area. This value changes as the user interacts with the **ChartControl** time-scale (x-axis).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/fromindex\#property-value)

An int representing the first bar index painted on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/fromindex\#syntax)

`ChartBars.FromIndex`

## [Examples](https://developer.ninjatrader.com/docs/desktop/fromindex\#examples)

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
}

```