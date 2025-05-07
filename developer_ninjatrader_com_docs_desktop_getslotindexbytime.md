## [Definition](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#definition)

Returns the slot index relative to the chart control corresponding to a specified time value.

## Note

Notes:

- A "Slot" is used in Equidistant [bar spacing](https://developer.ninjatrader.com/docs/desktop/barspacingtype) and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a TimeBased bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetBarIdxByTime()](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#method-return-value)

A double representing a slot index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#syntax)

`<chartcontrol>.GetSlotIndexByTime(DateTime time)`

## Warning

This method CANNOT be called on BarSpacingType.TimeBased charts. You will need to ensure an Equidistant [bar spacing type](https://developer.ninjatrader.com/docs/desktop/barspacingtype) is used, otherwise errors will be thrown.

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#method-parameters)

| Parameter | Description |
| --- | --- |
| **time** | A [DateTime](https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx) Structure used to determine a slot index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // ensure that GetSlotIndexByTime is called on TimeBased charts
    if(chartControl.BarSpacingType != BarSpacingType.TimeBased)
    {
        // get the slot index of the first time painted on the chart
        double slotIndex = chartControl.GetSlotIndexByTime(chartControl.FirstTimePainted);

        Print(slotIndex);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#definition)

Returns the slot index relative to the chart control corresponding to a specified time value.

## Note

Notes:

- A "Slot" is used in Equidistant [bar spacing](https://developer.ninjatrader.com/docs/desktop/barspacingtype) and represents a position on the chart canvas background which may or may not contain a bar. The concept of "Slots" does NOT exist on a TimeBased bar spacing type.
- If you are looking for information on a bar series, please see [ChartBars.GetBarIdxByTime()](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#method-return-value)

A double representing a slot index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#syntax)

`<chartcontrol>.GetSlotIndexByTime(DateTime time)`

## Warning

This method CANNOT be called on BarSpacingType.TimeBased charts. You will need to ensure an Equidistant [bar spacing type](https://developer.ninjatrader.com/docs/desktop/barspacingtype) is used, otherwise errors will be thrown.

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#method-parameters)

| Parameter | Description |
| --- | --- |
| **time** | A [DateTime](https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx) Structure used to determine a slot index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // ensure that GetSlotIndexByTime is called on TimeBased charts
    if(chartControl.BarSpacingType != BarSpacingType.TimeBased)
    {
        // get the slot index of the first time painted on the chart
        double slotIndex = chartControl.GetSlotIndexByTime(chartControl.FirstTimePainted);

        Print(slotIndex);
    }
}

```