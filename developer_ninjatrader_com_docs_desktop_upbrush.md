## [Definition](https://developer.ninjatrader.com/docs/desktop/upbrush\#definition)

A [Brush](https://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) object used to determine the color to paint the up bars for the ChartStyle.

This Windows Presentation Forms (WPF) implementation of the Brush class is not directly used to paint bars on the chart. Instead it is converted to a SharpDX Brush in the [UpBrushDX](https://developer.ninjatrader.com/docs/desktop/upbrushdx) property. This property is used to capture user input for changing brush colors.

## Note

## [Property  Value](https://developer.ninjatrader.com/docs/desktop/upbrush\#property-value)

A [WPF](https://msdn.microsoft.com/en-us/library/ms754130(v=vs.110).aspx) Brush object used to paint the up bars

## [Syntax](https://developer.ninjatrader.com/docs/desktop/upbrush\#syntax)

`UpBrush`

## [Examples](https://developer.ninjatrader.com/docs/desktop/upbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      // Set a new name for the UpBrush property
      SetPropertyName("UpBrush", "AdvancingBrush");
  }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/upbrush\#definition)

A [Brush](https://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) object used to determine the color to paint the up bars for the ChartStyle.

This Windows Presentation Forms (WPF) implementation of the Brush class is not directly used to paint bars on the chart. Instead it is converted to a SharpDX Brush in the [UpBrushDX](https://developer.ninjatrader.com/docs/desktop/upbrushdx) property. This property is used to capture user input for changing brush colors.

## Note

## [Property  Value](https://developer.ninjatrader.com/docs/desktop/upbrush\#property-value)

A [WPF](https://msdn.microsoft.com/en-us/library/ms754130(v=vs.110).aspx) Brush object used to paint the up bars

## [Syntax](https://developer.ninjatrader.com/docs/desktop/upbrush\#syntax)

`UpBrush`

## [Examples](https://developer.ninjatrader.com/docs/desktop/upbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      // Set a new name for the UpBrush property
      SetPropertyName("UpBrush", "AdvancingBrush");
  }
}

```