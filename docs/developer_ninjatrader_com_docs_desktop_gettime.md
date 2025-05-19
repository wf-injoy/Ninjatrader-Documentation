## [Definition](https://developer.ninjatrader.com/docs/desktop/gettime\#definition)

Returns the time stamp at the current bar index value.

## Note

This method will return what is displayed in the chart's data box. For formatting purposes, the value returned is NOT guaranteed to be equal to the **[TimeSeries](https://developer.ninjatrader.com/docs/desktop/timeseries)** value. If you are using daily bars and need the session end time, you should use **[Bars.GetSessionEndTime()](https://developer.ninjatrader.com/docs/desktop/getsessionendtime)** instead.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettime\#method-return-value)

A DateTime structure that represents the time stamp at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettime\#syntax)

`Bars.GetTime(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/gettime\#parameters)

| Parameter | Description |
| --- | --- |
| index | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);
    // loop through only the rendered bars on the chart
    for(int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
    {
        // get the time stamp at the selected bar index value
        DateTime timeValue = Bars.GetTime(barIndex);
        Print("Bar #" + barIndex + " time stamp is " + timeValue);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/gettime\#definition)

Returns the time stamp at the current bar index value.

## Note

This method will return what is displayed in the chart's data box. For formatting purposes, the value returned is NOT guaranteed to be equal to the **[TimeSeries](https://developer.ninjatrader.com/docs/desktop/timeseries)** value. If you are using daily bars and need the session end time, you should use **[Bars.GetSessionEndTime()](https://developer.ninjatrader.com/docs/desktop/getsessionendtime)** instead.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettime\#method-return-value)

A DateTime structure that represents the time stamp at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettime\#syntax)

`Bars.GetTime(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/gettime\#parameters)

| Parameter | Description |
| --- | --- |
| index | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);
    // loop through only the rendered bars on the chart
    for(int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
    {
        // get the time stamp at the selected bar index value
        DateTime timeValue = Bars.GetTime(barIndex);
        Print("Bar #" + barIndex + " time stamp is " + timeValue);
    }
}

```