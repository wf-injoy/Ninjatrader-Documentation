## [Definition](https://developer.ninjatrader.com/docs/desktop/downbrush\#definition)

A **Brush** object used to determine the color to paint the down bars for the ChartStyle.

## Note

This Windows Presentation Forms (WPF) implementation of the Brush class is not directly used to paint bars on the chart. Instead it is converted to a SharpDX Brush in the **DownBrushDX** property. This property is used to capture user input for changing brush colors.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/downbrush\#property-value)

A **WPF** Brush object used to paint the down bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/downbrush\#syntax)

`DownBrush`

## [Examples](https://developer.ninjatrader.com/docs/desktop/downbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Set a new name for the DownBrush property
        SetPropertyName("DownBrush", "DecliningBrush");
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/downbrush\#definition)

A **Brush** object used to determine the color to paint the down bars for the ChartStyle.

## Note

This Windows Presentation Forms (WPF) implementation of the Brush class is not directly used to paint bars on the chart. Instead it is converted to a SharpDX Brush in the **DownBrushDX** property. This property is used to capture user input for changing brush colors.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/downbrush\#property-value)

A **WPF** Brush object used to paint the down bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/downbrush\#syntax)

`DownBrush`

## [Examples](https://developer.ninjatrader.com/docs/desktop/downbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Set a new name for the DownBrush property
        SetPropertyName("DownBrush", "DecliningBrush");
    }
}

```