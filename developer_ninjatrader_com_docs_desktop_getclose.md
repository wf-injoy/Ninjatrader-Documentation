## [Definition](https://developer.ninjatrader.com/docs/desktop/getclose\#definition)

Returns the closing price at the current bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getclose\#method-return-value)

A **double** value that represents the close price at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getclose\#syntax)

`Bars.GetClose(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getclose\#parameters)

| **index** | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getclose\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through only the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex &lt;= ChartBars.ToIndex; barIndex++)
   {
     // get the close price at the selected bar index value
     double closePrice = Bars.GetClose(barIndex);
     Print("Bar #" + barIndex + " closing price is " + closePrice);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getclose\#definition)

Returns the closing price at the current bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getclose\#method-return-value)

A **double** value that represents the close price at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getclose\#syntax)

`Bars.GetClose(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getclose\#parameters)

| **index** | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getclose\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through only the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex &lt;= ChartBars.ToIndex; barIndex++)
   {
     // get the close price at the selected bar index value
     double closePrice = Bars.GetClose(barIndex);
     Print("Bar #" + barIndex + " closing price is " + closePrice);
   }
}

```