## [Definition](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#definition)

Returns a WPF coordinate on the chart determined by a series value represented on the chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#method-return-value)

An double value representing a WPF coordinate on the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#syntax)

`<chartscale>.GetYByValueWpf(double val)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#method-parameters)

| **val** | A **double** value which usually represents a price or indicator value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // gets the wpf coordinate of the price value passed to the method
   int     valueByYWpf = chartScale.GetYByValueWpf(Bars.GetClose(Bars.Count - 1));

   Print("valueByYWpf: " + valueByYWpf); // 207
}

```

In the image below, we pass the last bar close as the value (example logic avoids using a bars ago index, see also [**OnRender()**](https://developer.ninjatrader.com/docs/desktop/onrender) note #5), which in return tells us the last price displayed on the chart is at a WPF location of 207.30998 pixels.

## [Definition](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#definition)

Returns a WPF coordinate on the chart determined by a series value represented on the chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#method-return-value)

An double value representing a WPF coordinate on the chart scale.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#syntax)

`<chartscale>.GetYByValueWpf(double val)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#method-parameters)

| **val** | A **double** value which usually represents a price or indicator value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getybyvaluewpf\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // gets the wpf coordinate of the price value passed to the method
   int     valueByYWpf = chartScale.GetYByValueWpf(Bars.GetClose(Bars.Count - 1));

   Print("valueByYWpf: " + valueByYWpf); // 207
}

```

In the image below, we pass the last bar close as the value (example logic avoids using a bars ago index, see also [**OnRender()**](https://developer.ninjatrader.com/docs/desktop/onrender) note #5), which in return tells us the last price displayed on the chart is at a WPF location of 207.30998 pixels.