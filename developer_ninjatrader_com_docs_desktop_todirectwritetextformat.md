## [Definition](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#definition)

Converts a **SimpleFont** object to a **SharpDX** compatible font which can be used for chart rendering.

## Note

For more information please see the educational resource on [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#method-return-value)

A **DirectWrite.TextFormat** object

## Warning

The returned DirectWrite.TextFormat object should be disposed of immediately when finished drawing text.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#syntax)

`<simplefont>.ToDirectWriteTextFormat()`

## [Examples](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Set text to chart label simple font object
   SharpDX.DirectWrite.TextFormat textFormat = chartControl.Properties.LabelFont.ToDirectWriteTextFormat();

   // use the textFormat in a RenderTarget.DrawText() or DrawTextLayout() method

   // do not forget to dispose text format when finished
   textFormat.Dispose();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#definition)

Converts a **SimpleFont** object to a **SharpDX** compatible font which can be used for chart rendering.

## Note

For more information please see the educational resource on [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#method-return-value)

A **DirectWrite.TextFormat** object

## Warning

The returned DirectWrite.TextFormat object should be disposed of immediately when finished drawing text.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#syntax)

`<simplefont>.ToDirectWriteTextFormat()`

## [Examples](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Set text to chart label simple font object
   SharpDX.DirectWrite.TextFormat textFormat = chartControl.Properties.LabelFont.ToDirectWriteTextFormat();

   // use the textFormat in a RenderTarget.DrawText() or DrawTextLayout() method

   // do not forget to dispose text format when finished
   textFormat.Dispose();
}

```