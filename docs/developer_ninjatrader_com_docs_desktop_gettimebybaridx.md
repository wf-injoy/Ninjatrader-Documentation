## [Definition](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#definition)

Returns the **ChartBars** time value calculated from a bar index parameter provided.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#method-return-value)

A **DateTime** struct representing a bar time value at a specific bar index value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#syntax)

`ChartBars.GetTimeByBarIdx(ChartControl chartControl, int barIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#method-parameters)

| **chartControl** | The **ChartControl** object used to determine the chart's time axis |
| **barIndex** | An **int** value representing a bar index used to convert to a **ChartBar** index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (ChartBars != null)
   {
     Print(ChartBars.GetTimeByBarIdx(ChartControl, 50)); //8/11/2015 4:30:00 AM
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#definition)

Returns the **ChartBars** time value calculated from a bar index parameter provided.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#method-return-value)

A **DateTime** struct representing a bar time value at a specific bar index value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#syntax)

`ChartBars.GetTimeByBarIdx(ChartControl chartControl, int barIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#method-parameters)

| **chartControl** | The **ChartControl** object used to determine the chart's time axis |
| **barIndex** | An **int** value representing a bar index used to convert to a **ChartBar** index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (ChartBars != null)
   {
     Print(ChartBars.GetTimeByBarIdx(ChartControl, 50)); //8/11/2015 4:30:00 AM
   }
}

```