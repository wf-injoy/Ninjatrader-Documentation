## [Definition](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#definition)

Indicates the most recent (last) slot index of the Data Series on the chart, regardless if a bar is actually painted in that slot.

## Note

LastSlotPainted differs from **ChartBars.ToIndex**, which returns the last index containing a bar painted in the visible area of the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#property-value)

A int representing the most recent (last) slot index on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#syntax)

`<chartcontrol>.LastSlotPainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   int lastSlot = chartControl.LastSlotPainted;

   // Print the index of the last slot on the chart
   Print(lastSlot);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#definition)

Indicates the most recent (last) slot index of the Data Series on the chart, regardless if a bar is actually painted in that slot.

## Note

LastSlotPainted differs from **ChartBars.ToIndex**, which returns the last index containing a bar painted in the visible area of the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#property-value)

A int representing the most recent (last) slot index on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#syntax)

`<chartcontrol>.LastSlotPainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lastslotpainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   int lastSlot = chartControl.LastSlotPainted;

   // Print the index of the last slot on the chart
   Print(lastSlot);
}

```