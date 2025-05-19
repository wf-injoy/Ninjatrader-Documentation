## [Definition](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#definition)

Returns the chart-canvas x-coordinate of the bar at a specified index of a specified **ChartBars** object on the chart.

## Note

Since the index is based upon bars that move across the chart canvas as new bars are painted, the value returned by **GetXByBarIndex()** can be expected to change as new bars are painted on the chart, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#method-return-value)

An int representing a chart-canvas x-coordinate.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#syntax)

`<chartcontrol>.GetXByBarIndex(ChartBars chartBars, int barIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#method-parameters)

| **Parameter** | **Description** |
| --- | --- |
| **chartBars** | The **ChartBars** object to check. |
| **barIndex** | The slot index used to determine an x-coordinate. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    double xCoordinate = chartControl.GetXByBarIndex(ChartBars, 100);

    // Print the x-coordinate value
    Print(xCoordinate);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#definition)

Returns the chart-canvas x-coordinate of the bar at a specified index of a specified **ChartBars** object on the chart.

## Note

Since the index is based upon bars that move across the chart canvas as new bars are painted, the value returned by **GetXByBarIndex()** can be expected to change as new bars are painted on the chart, or as the chart is scrolled backward or forward on the x-axis.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#method-return-value)

An int representing a chart-canvas x-coordinate.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#syntax)

`<chartcontrol>.GetXByBarIndex(ChartBars chartBars, int barIndex)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#method-parameters)

| **Parameter** | **Description** |
| --- | --- |
| **chartBars** | The **ChartBars** object to check. |
| **barIndex** | The slot index used to determine an x-coordinate. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getxbybarindex\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    double xCoordinate = chartControl.GetXByBarIndex(ChartBars, 100);

    // Print the x-coordinate value
    Print(xCoordinate);
}

```