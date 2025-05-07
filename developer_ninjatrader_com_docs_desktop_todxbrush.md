## [Definition](https://developer.ninjatrader.com/docs/desktop/todxbrush\#definition)

Converts a WPF Brush to a SharpDX Brush used for **SharpDX rendering**. Supports **SolidColorBrush**, **LinearGradientBrush**, and **RadialGradientBrush** types.

## Note

If you are using a large number of brushes, and are not tied to WPF resources, you should favor creating the SharpDX Brush directly since the ToDxBrush() method can lead to performance issues if called too frequently during a single render pass.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/todxbrush\#method-return-value)

A new **SharpDX.Direct2D1.Brush** constructed colors and brush properties of the WPF brush.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/todxbrush\#syntax)

`DxExtensions.ToDxBrush(this System.Windows.Media.Brush brush, RenderTarget renderTarget)`

`<wpfbrush>.ToDxBrush(RenderTarget renderTarget)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/todxbrush\#parameters)

| brush | The **System.Windows.Media.Brush** to convert |
| renderTarget | The **RenderTarget** associated with the brush resource |

## [Examples](https://developer.ninjatrader.com/docs/desktop/todxbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "Example ToDXBrush";

        // pushes the WPF brush to the UI for user to configure
        TextBrush = System.Windows.Media.Brushes.DodgerBlue;
    }
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // convert user WPF selection to a DX brush
    SharpDX.Direct2D1.Brush dxBrush = TextBrush.ToDxBrush(RenderTarget);

    using (dxBrush)
    {
        RenderTarget.FillRectangle(new RectangleF(ChartPanel.X, ChartPanel.Y, ChartPanel.W, ChartPanel.H), dxBrush);
    }
}

// the WPF exposed to the UI which the user defines
[XmlIgnore]
public System.Windows.Media.Brush TextBrush { get; set; }

[Browsable(false)]
public string TextBrushSerialize
{
    get { return Serialize.BrushToString(TextBrush); }
    set { TextBrush = Serialize.StringToBrush(value); }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/todxbrush\#definition)

Converts a WPF Brush to a SharpDX Brush used for **SharpDX rendering**. Supports **SolidColorBrush**, **LinearGradientBrush**, and **RadialGradientBrush** types.

## Note

If you are using a large number of brushes, and are not tied to WPF resources, you should favor creating the SharpDX Brush directly since the ToDxBrush() method can lead to performance issues if called too frequently during a single render pass.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/todxbrush\#method-return-value)

A new **SharpDX.Direct2D1.Brush** constructed colors and brush properties of the WPF brush.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/todxbrush\#syntax)

`DxExtensions.ToDxBrush(this System.Windows.Media.Brush brush, RenderTarget renderTarget)`

`<wpfbrush>.ToDxBrush(RenderTarget renderTarget)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/todxbrush\#parameters)

| brush | The **System.Windows.Media.Brush** to convert |
| renderTarget | The **RenderTarget** associated with the brush resource |

## [Examples](https://developer.ninjatrader.com/docs/desktop/todxbrush\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "Example ToDXBrush";

        // pushes the WPF brush to the UI for user to configure
        TextBrush = System.Windows.Media.Brushes.DodgerBlue;
    }
}

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // convert user WPF selection to a DX brush
    SharpDX.Direct2D1.Brush dxBrush = TextBrush.ToDxBrush(RenderTarget);

    using (dxBrush)
    {
        RenderTarget.FillRectangle(new RectangleF(ChartPanel.X, ChartPanel.Y, ChartPanel.W, ChartPanel.H), dxBrush);
    }
}

// the WPF exposed to the UI which the user defines
[XmlIgnore]
public System.Windows.Media.Brush TextBrush { get; set; }

[Browsable(false)]
public string TextBrushSerialize
{
    get { return Serialize.BrushToString(TextBrush); }
    set { TextBrush = Serialize.StringToBrush(value); }
}

```