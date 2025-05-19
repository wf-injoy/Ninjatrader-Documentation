## [Definition](https://developer.ninjatrader.com/docs/desktop/createanchor\#definition)

Used to create a new chart anchor at a specified mouse point.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/createanchor\#method-return-value)

A new **ChartAnchor** at a specified point in device pixels.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/createanchor\#syntax)

`CreateAnchor(Point point, ChartControl chartControl, ChartScale chartScale)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/createanchor\#method-parameters)

| **point** | A Point in device pixels representing the current mouse cursor position |
| **chartControl** | A ChartControl representing the x-axis |
| **chartScale** | A ChartScale representing the y-axis |

## [Examples](https://developer.ninjatrader.com/docs/desktop/createanchor\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)**
{
   // get the point where the mouse was clicked
   Point myPoint = dataPoint.GetPoint(chartControl, chartPanel, chartScale);

   // create an anchor at that point
   ChartAnchor MyAnchor = CreateAnchor(myPoint, chartControl, chartScale);

   Print(MyAnchor.Time); // 3/16/2015 8:18:48 AM
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/createanchor\#definition)

Used to create a new chart anchor at a specified mouse point.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/createanchor\#method-return-value)

A new **ChartAnchor** at a specified point in device pixels.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/createanchor\#syntax)

`CreateAnchor(Point point, ChartControl chartControl, ChartScale chartScale)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/createanchor\#method-parameters)

| **point** | A Point in device pixels representing the current mouse cursor position |
| **chartControl** | A ChartControl representing the x-axis |
| **chartScale** | A ChartScale representing the y-axis |

## [Examples](https://developer.ninjatrader.com/docs/desktop/createanchor\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)**
{
   // get the point where the mouse was clicked
   Point myPoint = dataPoint.GetPoint(chartControl, chartPanel, chartScale);

   // create an anchor at that point
   ChartAnchor MyAnchor = CreateAnchor(myPoint, chartControl, chartScale);

   Print(MyAnchor.Time); // 3/16/2015 8:18:48 AM
}

```