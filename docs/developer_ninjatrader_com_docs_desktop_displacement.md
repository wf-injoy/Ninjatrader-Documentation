## [Definition](https://developer.ninjatrader.com/docs/desktop/displacement\#definition)

An offset value that shifts the visually displayed value of an indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displacement\#property-value)

An **int** value that represents the number of bars ago to offset with.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displacement\#syntax)

`Displacement`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displacement\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Displacement = 2; // Plots the indicator value from 2 bars ago on the current bar
        AddPlot(Brushes.Orange, "SMA");
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/displacement\#definition)

An offset value that shifts the visually displayed value of an indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displacement\#property-value)

An **int** value that represents the number of bars ago to offset with.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displacement\#syntax)

`Displacement`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displacement\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Displacement = 2; // Plots the indicator value from 2 bars ago on the current bar
        AddPlot(Brushes.Orange, "SMA");
    }
}

```