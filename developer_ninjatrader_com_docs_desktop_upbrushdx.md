## [Definition](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#definition)

A SharpDX [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) object used to paint the up bars for the ChartStyle.

## [Property  Value](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#property-value)

A [SharpDX](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) Brush object used to paint the up bars

## [Syntax](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#syntax)

`UpBrushDX`

## [Examples](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)
{
  for (int idx = chartBars.FromIndex; idx <= chartBars.ToIndex; idx++)
      {
          double     closeValue             = bars.GetClose(idx);
          double     openValue               = bars.GetOpen(idx);

          // Set the brush of the current candle to UpBrushDX or DownBrushDX, depending on the
          // bar direction
          Brush brush = closeValue >= openValue ? UpBrushDX : DownBrushDX;
      }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#definition)

A SharpDX [Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) object used to paint the up bars for the ChartStyle.

## [Property  Value](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#property-value)

A [SharpDX](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1) Brush object used to paint the up bars

## [Syntax](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#syntax)

`UpBrushDX`

## [Examples](https://developer.ninjatrader.com/docs/desktop/upbrushdx\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)
{
  for (int idx = chartBars.FromIndex; idx <= chartBars.ToIndex; idx++)
      {
          double     closeValue             = bars.GetClose(idx);
          double     openValue               = bars.GetOpen(idx);

          // Set the brush of the current candle to UpBrushDX or DownBrushDX, depending on the
          // bar direction
          Brush brush = closeValue >= openValue ? UpBrushDX : DownBrushDX;
      }
}

```