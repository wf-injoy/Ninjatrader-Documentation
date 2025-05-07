## [Definition](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#definition)

Returns the **ChartBars** index value calculated from the time parameter provided.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#method-return-value)

An **int** representing the bar index value at a specific time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#syntax)

`ChartBars.GetBarIdxByTime(ChartControl chartControl, DateTime time)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#method-parameters)

| **chartControl** | The **ChartControl** object used to determine the chart's time axis |
| **time** | The **DateTime** value used to convert to a ChartBar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#examples)

```jsx-150469391 csharp

protected override void OnBarUpdate()
{
   if (ChartBars != null)
   {
     Print(ChartBars.GetBarIdxByTime(ChartControl, Time[0]));
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#definition)

Returns the **ChartBars** index value calculated from the time parameter provided.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#method-return-value)

An **int** representing the bar index value at a specific time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#syntax)

`ChartBars.GetBarIdxByTime(ChartControl chartControl, DateTime time)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#method-parameters)

| **chartControl** | The **ChartControl** object used to determine the chart's time axis |
| **time** | The **DateTime** value used to convert to a ChartBar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime\#examples)

```jsx-150469391 csharp

protected override void OnBarUpdate()
{
   if (ChartBars != null)
   {
     Print(ChartBars.GetBarIdxByTime(ChartControl, Time[0]));
   }
}

```