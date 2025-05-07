## [Definition](https://developer.ninjatrader.com/docs/desktop/getxbytime\#definition)

Returns the chart-canvas x-coordinate of the slot index of the primary **Bars** object corresponding to a specified time.

## Note

Since the time correlates with a specific bar index, and since bars move on the chart canvas as new bars are painted, the value returned by **GetXByTime()** can be expected to change as new bars are painted on the chart, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getxbytime\#method-return-value)

An int representing a chart-canvas x-coordinate.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getxbytime\#syntax)

`<chartcontrol>.GetXByTime(DateTime time)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getxbytime\#method-parameters)

| time | A **DateTime** object used to determine an x-coordinate |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getxbytime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   DateTime timeToCheck = new DateTime(2017, 8, 6, 11, 0, 0);

   // Find the chart-canvas x-coordinate of the bar at the specified time
    int xCoordinate = chartControl.GetXByTime(timeToCheck);

   // Print the x-coordinate value
   Print(xCoordinate);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getxbytime\#definition)

Returns the chart-canvas x-coordinate of the slot index of the primary **Bars** object corresponding to a specified time.

## Note

Since the time correlates with a specific bar index, and since bars move on the chart canvas as new bars are painted, the value returned by **GetXByTime()** can be expected to change as new bars are painted on the chart, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getxbytime\#method-return-value)

An int representing a chart-canvas x-coordinate.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getxbytime\#syntax)

`<chartcontrol>.GetXByTime(DateTime time)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getxbytime\#method-parameters)

| time | A **DateTime** object used to determine an x-coordinate |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getxbytime\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   DateTime timeToCheck = new DateTime(2017, 8, 6, 11, 0, 0);

   // Find the chart-canvas x-coordinate of the bar at the specified time
    int xCoordinate = chartControl.GetXByTime(timeToCheck);

   // Print the x-coordinate value
   Print(xCoordinate);
}

```