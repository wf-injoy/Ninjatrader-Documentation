## [Definition](https://developer.ninjatrader.com/docs/desktop/getopen\#definition)

Returns the open price at the selected bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getopen\#method-return-value)

A **double** value that represents the open price at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getopen\#syntax)

`Bars.GetOpen(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getopen\#parameters)

| **index** | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getopen\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through only the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
   {
     // get the open price at the selected bar index value
     double openPrice = Bars.GetOpen(barIndex);
     Print("Bar #" + barIndex + " open price is " + openPrice);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getopen\#definition)

Returns the open price at the selected bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getopen\#method-return-value)

A **double** value that represents the open price at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getopen\#syntax)

`Bars.GetOpen(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getopen\#parameters)

| **index** | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getopen\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through only the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex <= ChartBars.ToIndex; barIndex++)
   {
     // get the open price at the selected bar index value
     double openPrice = Bars.GetOpen(barIndex);
     Print("Bar #" + barIndex + " open price is " + openPrice);
   }
}

```