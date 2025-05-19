## [Definition](https://developer.ninjatrader.com/docs/desktop/slotspainted\#definition)

Indicates the number of index slots in which bars are painted within the chart canvas area. This covers the visible portion of the chart only, and does not include historical painted bars outside of the visible area.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/slotspainted\#property-value)

An int representing the number of index slots in which bars are painted.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/slotspainted\#syntax)

`<chartcontrol>.SlotsPainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/slotspainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   int painted = chartControl.SlotsPainted;

   // Print the number of bars painted on the visible chart canvas
   Print(painted);
}

```

In the image below, **SlotsPainted** reveals that there are 17 bars painted on the chart canvas.

## [Definition](https://developer.ninjatrader.com/docs/desktop/slotspainted\#definition)

Indicates the number of index slots in which bars are painted within the chart canvas area. This covers the visible portion of the chart only, and does not include historical painted bars outside of the visible area.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/slotspainted\#property-value)

An int representing the number of index slots in which bars are painted.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/slotspainted\#syntax)

`<chartcontrol>.SlotsPainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/slotspainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   int painted = chartControl.SlotsPainted;

   // Print the number of bars painted on the visible chart canvas
   Print(painted);
}

```

In the image below, **SlotsPainted** reveals that there are 17 bars painted on the chart canvas.