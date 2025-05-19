## [Definition](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#definition)

Determines if plot(s) display in the chart data box.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#property-value)

This property returns true if the indicator plot(s) values display in the chart data box; otherwise, false. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#syntax)

`DisplayInDataBox`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        DisplayInDataBox = false;
        AddPlot(Brushes.Orange, "SMA");
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#definition)

Determines if plot(s) display in the chart data box.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#property-value)

This property returns true if the indicator plot(s) values display in the chart data box; otherwise, false. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#syntax)

`DisplayInDataBox`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displayindatabox\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        DisplayInDataBox = false;
        AddPlot(Brushes.Orange, "SMA");
    }
}

```