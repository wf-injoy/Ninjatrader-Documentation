## [Definition](https://developer.ninjatrader.com/docs/desktop/getpoint\#definition)

Returns a chart anchor's data point in device pixels

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getpoint\#method-return-value)

A **Point** structure; a point value in device pixels for a chart's given panel & scale

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getpoint\#syntax)

`<chartanchor>.GetPoint(ChartControl chartControl, ChartPanel chartPanel, ChartScale, bool pixelAlign)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getpoint\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing a panel of the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **pixelAlign** | An optional bool determining if the data point should be rounded to the closest .5 pixel point |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getpoint\#examples)

```jsx-150469391 csharp
//gets the chart anchor's data points
Point anchorPoint = MyAnchor.GetPoint(chartControl, chartPanel, chartScale);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getpoint\#definition)

Returns a chart anchor's data point in device pixels

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getpoint\#method-return-value)

A **Point** structure; a point value in device pixels for a chart's given panel & scale

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getpoint\#syntax)

`<chartanchor>.GetPoint(ChartControl chartControl, ChartPanel chartPanel, ChartScale, bool pixelAlign)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getpoint\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing a panel of the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **pixelAlign** | An optional bool determining if the data point should be rounded to the closest .5 pixel point |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getpoint\#examples)

```jsx-150469391 csharp
//gets the chart anchor's data points
Point anchorPoint = MyAnchor.GetPoint(chartControl, chartPanel, chartScale);

```