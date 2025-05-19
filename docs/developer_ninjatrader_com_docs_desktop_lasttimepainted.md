## [Definition](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#definition)

Indicates the time of the most recently painted bar on the primary **Bars** object configured on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#property-value)

A **DateTime** object corresponding to the slot index of the most recently painted bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#syntax)

`<chartcontrol` >.LastTimePainted\`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   DateTime lastSlotTime = chartControl.LastTimePainted;

   // Print the index of the last slot painted on the chart
   Print(lastSlotTime);
}

```

In the image below, LastTimePainted reveals that the last index painted on the chart corresponds to 8/12/17 at 2:10:00 PM.

## [Definition](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#definition)

Indicates the time of the most recently painted bar on the primary **Bars** object configured on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#property-value)

A **DateTime** object corresponding to the slot index of the most recently painted bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#syntax)

`<chartcontrol` >.LastTimePainted\`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lasttimepainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   DateTime lastSlotTime = chartControl.LastTimePainted;

   // Print the index of the last slot painted on the chart
   Print(lastSlotTime);
}

```

In the image below, LastTimePainted reveals that the last index painted on the chart corresponds to 8/12/17 at 2:10:00 PM.