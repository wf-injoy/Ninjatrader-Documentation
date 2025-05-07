## [Definition](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#definition)

If true, any indicator plot values display price markers in the y-axis.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#property-value)

This property returns true if the indicator plot values display in the y-axis; otherwise, false. Default set to true.

## Warning

Warning: This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#syntax)

`PaintPriceMarkers`

## [Examples](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         PaintPriceMarkers = true; // Indicator plots values display in the y-axis
         AddPlot(Brushes.Orange, "SMA");
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#definition)

If true, any indicator plot values display price markers in the y-axis.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#property-value)

This property returns true if the indicator plot values display in the y-axis; otherwise, false. Default set to true.

## Warning

Warning: This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#syntax)

`PaintPriceMarkers`

## [Examples](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         PaintPriceMarkers = true; // Indicator plots values display in the y-axis
         AddPlot(Brushes.Orange, "SMA");
     }
}

```