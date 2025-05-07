## [Definition](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#definition)

Returns the chart's y-pixel coordinate on the chart determined by a series value represented on the chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#method-return-value)

An **int** value representing a y pixel coordinate on the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#syntax)

`<chartscale>.GetYByValue(double val)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#method-parameters)

| **val** | A **double** value which usually represents a price or indicator value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // gets the pixel coordinate of the price value passed to the method
   int     yByValue = chartScale.GetYByValue(Bars.GetClose(Bars.Count - 1));

   Print("yByValue: " + yByValue); // 207
}

```

In the image below, we pass the last bar close as the value (example logic avoids using a bars ago index, see also [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) note #5), which in return tells us the last price displayed on the chart is at a y location of 207 pixels.

## [Definition](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#definition)

Returns the chart's y-pixel coordinate on the chart determined by a series value represented on the chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#method-return-value)

An **int** value representing a y pixel coordinate on the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#syntax)

`<chartscale>.GetYByValue(double val)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#method-parameters)

| **val** | A **double** value which usually represents a price or indicator value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getybyvalue\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // gets the pixel coordinate of the price value passed to the method
   int     yByValue = chartScale.GetYByValue(Bars.GetClose(Bars.Count - 1));

   Print("yByValue: " + yByValue); // 207
}

```

In the image below, we pass the last bar close as the value (example logic avoids using a bars ago index, see also [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) note #5), which in return tells us the last price displayed on the chart is at a y location of 207 pixels.