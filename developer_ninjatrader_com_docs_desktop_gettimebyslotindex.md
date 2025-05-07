## [Definition](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#definition)

Returns a time value relative to the chart control corresponding to a specified slot index.

## Note

Notes:

- A "Slot" is used in Equidistant **bar spacing** and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a TimeBased bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetTimeByBarIdx()](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx).
- For slot index values in the future, an estimation of time will be returned. It is not possible to predict the future time of a bar for all bar series (i.e., tick/volume based bars).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#method-return-value)

A **DateTime** object corresponding to a specified slot index; returns **DateTime** value for 'now' on a time based bar spacing type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#syntax)

`<chartcontrol>.GetTimeBySlotIndex(double slotIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#method-parameters)

| slotIndex | The slot index used to determine a time value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Find the timestamp of the bar at index 150
    DateTime slotTime = chartControl.GetTimeBySlotIndex(150);

    // Print the date of slotTime
    Print(slotTime.Date);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#definition)

Returns a time value relative to the chart control corresponding to a specified slot index.

## Note

Notes:

- A "Slot" is used in Equidistant **bar spacing** and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a TimeBased bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetTimeByBarIdx()](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx).
- For slot index values in the future, an estimation of time will be returned. It is not possible to predict the future time of a bar for all bar series (i.e., tick/volume based bars).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#method-return-value)

A **DateTime** object corresponding to a specified slot index; returns **DateTime** value for 'now' on a time based bar spacing type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#syntax)

`<chartcontrol>.GetTimeBySlotIndex(double slotIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#method-parameters)

| slotIndex | The slot index used to determine a time value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Find the timestamp of the bar at index 150
    DateTime slotTime = chartControl.GetTimeBySlotIndex(150);

    // Print the date of slotTime
    Print(slotTime.Date);
}

```