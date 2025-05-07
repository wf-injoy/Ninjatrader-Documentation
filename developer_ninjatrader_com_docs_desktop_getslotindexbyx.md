## [Definition](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#definition)

Returns the slot index relative to the chart control corresponding to a specified x-coordinate.

## Note

- A "Slot" is used in Equidistant **bar spacing** and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a **TimeBased** bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetBarIdxByX()](https://developer.ninjatrader.com/docs/desktop/getbaridxbyx).
- Since the slot index is based on the chart canvas, the value returned by **GetSlotIndexByX()** can be expected to change as new bars are painted, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#method-return-value)

A double representing a slot index; returns -1 on a time based bar spacing type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#syntax)

`<chartcontrol>.GetSlotIndexByX(int x)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#method-parameters)

| x | An int used to determine a slot index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Find the index of the bar painted at x-coordinate 35
    double slotIndex = chartControl.GetSlotIndexByX(35);

    // Print the slot index of the specified time
    Print(slotIndex);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#definition)

Returns the slot index relative to the chart control corresponding to a specified x-coordinate.

## Note

- A "Slot" is used in Equidistant **bar spacing** and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a **TimeBased** bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetBarIdxByX()](https://developer.ninjatrader.com/docs/desktop/getbaridxbyx).
- Since the slot index is based on the chart canvas, the value returned by **GetSlotIndexByX()** can be expected to change as new bars are painted, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#method-return-value)

A double representing a slot index; returns -1 on a time based bar spacing type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#syntax)

`<chartcontrol>.GetSlotIndexByX(int x)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#method-parameters)

| x | An int used to determine a slot index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Find the index of the bar painted at x-coordinate 35
    double slotIndex = chartControl.GetSlotIndexByX(35);

    // Print the slot index of the specified time
    Print(slotIndex);
}

```