## [Definition](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#definition)

Determines if plot(s) values which are set to a **Transparent** brush display in the chart data box. The default behavior is to hide any plots which have been configured as a **Transparent** brush, however this behavior can be changed by setting **ShowTransparentPlotsInDataBox** to true on the indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#property-value)

This property returns true if transparent indicator plot(s) values display in the chart data box; otherwise, false. Default set to false.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#syntax)

`ShowTransparentPlotsInDataBox`

## [Examples](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         ShowTransparentPlotsInDataBox = true;
         AddPlot(Brushes.Transparent, "MyPlot");
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#definition)

Determines if plot(s) values which are set to a **Transparent** brush display in the chart data box. The default behavior is to hide any plots which have been configured as a **Transparent** brush, however this behavior can be changed by setting **ShowTransparentPlotsInDataBox** to true on the indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#property-value)

This property returns true if transparent indicator plot(s) values display in the chart data box; otherwise, false. Default set to false.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#syntax)

`ShowTransparentPlotsInDataBox`

## [Examples](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         ShowTransparentPlotsInDataBox = true;
         AddPlot(Brushes.Transparent, "MyPlot");
     }
}

```