## [Definition](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#definition)

Plots horizontal grid lines on the indicator panel.

## Note

The indicator panel's parent chart has a similar option 'Grid line - horizontal' which if Visible property set to false, will override the indicator's local setting if true.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#property-value)

This property returns true if horizontal grid lines are plotted on the indicator panel; otherwise, false. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#syntax)

`DrawHorizontalGridLines`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         DrawHorizontalGridLines = false; // Horizontal grid lines will not plot on the indicator panel
         AddPlot(Brushes.Orange, "SMA");
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#definition)

Plots horizontal grid lines on the indicator panel.

## Note

The indicator panel's parent chart has a similar option 'Grid line - horizontal' which if Visible property set to false, will override the indicator's local setting if true.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#property-value)

This property returns true if horizontal grid lines are plotted on the indicator panel; otherwise, false. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#syntax)

`DrawHorizontalGridLines`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         DrawHorizontalGridLines = false; // Horizontal grid lines will not plot on the indicator panel
         AddPlot(Brushes.Orange, "SMA");
     }
}

```