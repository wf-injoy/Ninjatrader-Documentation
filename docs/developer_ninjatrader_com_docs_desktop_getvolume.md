## [Definition](https://developer.ninjatrader.com/docs/desktop/getvolume\#definition)

Returns the volume at the selected bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getvolume\#method-return-value)

A long value represents the volume at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getvolume\#syntax)

`Bars.GetVolume(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getvolume\#parameters)

| index | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getvolume\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through all the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex &lt;= ChartBars.ToIndex; barIndex++)
   {
     // get the volume value at the selected bar index value
     long volumeValue = Bars.GetVolume(barIndex);
     Print("Bar #" + barIndex + " volume value is " + volumeValue);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getvolume\#definition)

Returns the volume at the selected bar index value.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getvolume\#method-return-value)

A long value represents the volume at the desired bar index.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getvolume\#syntax)

`Bars.GetVolume(int index)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getvolume\#parameters)

| index | An int representing an absolute bar index value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getvolume\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   base.OnRender(chartControl, chartScale);
   // loop through all the rendered bars on the chart
   for(int barIndex = ChartBars.FromIndex; barIndex &lt;= ChartBars.ToIndex; barIndex++)
   {
     // get the volume value at the selected bar index value
     long volumeValue = Bars.GetVolume(barIndex);
     Print("Bar #" + barIndex + " volume value is " + volumeValue);
   }
}

```