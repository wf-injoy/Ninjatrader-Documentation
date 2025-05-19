## [Definition](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#definition)

Returns the series value on the chart scale determined by a WPF coordinate on the chart.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#method-return-value)

A **double** value representing a series value on the chart scale. This is normally a price value, but can represent indicator plot values as well.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#syntax)

`<chartscale>.GetValueByYWpf(double y)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#method-parameters)

| **y** | A **double** value representing a WPF coordinate on the chart scale |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // store the y location the user clicked
   double   wpfY = chartControl.MouseDownPoint.Y;

   // gets price value of the WPF coordinate passed to the method
   double   valueByYWpf = chartScale.GetValueByYWpf(wpfY);

   Print("valueByYWpf: " + valueByYWpf); //2105.49995215
}

```

In the image below, we used the Chart Control property **MouseDownPoint** as the "wpfy" variable, which in return tells us the user clicked on a Y value of 2105.499 on the chart scale.

## [Definition](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#definition)

Returns the series value on the chart scale determined by a WPF coordinate on the chart.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#method-return-value)

A **double** value representing a series value on the chart scale. This is normally a price value, but can represent indicator plot values as well.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#syntax)

`<chartscale>.GetValueByYWpf(double y)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#method-parameters)

| **y** | A **double** value representing a WPF coordinate on the chart scale |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getvaluebyywpf\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // store the y location the user clicked
   double   wpfY = chartControl.MouseDownPoint.Y;

   // gets price value of the WPF coordinate passed to the method
   double   valueByYWpf = chartScale.GetValueByYWpf(wpfY);

   Print("valueByYWpf: " + valueByYWpf); //2105.49995215
}

```

In the image below, we used the Chart Control property **MouseDownPoint** as the "wpfy" variable, which in return tells us the user clicked on a Y value of 2105.499 on the chart scale.