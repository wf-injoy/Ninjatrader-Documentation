## [Definition](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#definition)

Returns the closest chart anchor within a specified maximum distance from the mouse cursor.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#method-return-value)

This method returns an existing **ChartAnchor**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#syntax)

`GetClosestAnchor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, double maxDist, Point point)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#method-parameters)

| **chartControl** | A **ChartControl** representing the x-axis |
| **chartPanel** | A **ChartPanel** representing the panel for the chart |
| **chartScale** | A **ChartScale** representing the y-axis |
| **maxDist** | A **double** value representing the cursor's sensitivity used to detect the nearest anchor |
| **point** | A **Point** in device pixels representing the current mouse cursor position |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#examples)

```jsx-150469391 csharp

public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   // get the closest anchor to where the user has clicked
   ChartAnchor closest = GetClosestAnchor(chartControl, chartPanel, chartScale, 10, point);

   if (closest != null)
   {
     // set cursor to indicate that it can be moved
     return Cursors.SizeNWSE;
   }
   // otherwise set cursor back to arrow
   else return Cursors.Arrow;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#definition)

Returns the closest chart anchor within a specified maximum distance from the mouse cursor.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#method-return-value)

This method returns an existing **ChartAnchor**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#syntax)

`GetClosestAnchor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, double maxDist, Point point)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#method-parameters)

| **chartControl** | A **ChartControl** representing the x-axis |
| **chartPanel** | A **ChartPanel** representing the panel for the chart |
| **chartScale** | A **ChartScale** representing the y-axis |
| **maxDist** | A **double** value representing the cursor's sensitivity used to detect the nearest anchor |
| **point** | A **Point** in device pixels representing the current mouse cursor position |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getclosestanchor\#examples)

```jsx-150469391 csharp

public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   // get the closest anchor to where the user has clicked
   ChartAnchor closest = GetClosestAnchor(chartControl, chartPanel, chartScale, 10, point);

   if (closest != null)
   {
     // set cursor to indicate that it can be moved
     return Cursors.SizeNWSE;
   }
   // otherwise set cursor back to arrow
   else return Cursors.Arrow;

```