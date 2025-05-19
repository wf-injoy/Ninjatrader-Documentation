## [Definition](https://developer.ninjatrader.com/docs/desktop/lines\#definition)

A collection holding all of the Line objects that define the visualization characteristics oscillator lines of the indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lines\#property-value)

A collection of Line objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lines\#syntax)

`Lines[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lines\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         // Lines are added to the Lines collection in order
         AddLine(Brushes.Gray, 30, "Lower"); // Stored in Lines[0]
         AddLine(Brushes.Gray, 70, "Upper"); // Stored in Lines[1]
     }
}
// Dynamically change the upper line's color and thickness based on the indicator value
protected override void OnBarUpdate()
{
   if (Value[0] > 70)
   {
     Lines[1].Brush = Brushes.Blue;
     Lines[1].Width = 3;
   }
   else
   {
     Lines[1].Brush = Brushes.Gray;
     Lines[1].Width = 1;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/lines\#definition)

A collection holding all of the Line objects that define the visualization characteristics oscillator lines of the indicator.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/lines\#property-value)

A collection of Line objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/lines\#syntax)

`Lines[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/lines\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         // Lines are added to the Lines collection in order
         AddLine(Brushes.Gray, 30, "Lower"); // Stored in Lines[0]
         AddLine(Brushes.Gray, 70, "Upper"); // Stored in Lines[1]
     }
}
// Dynamically change the upper line's color and thickness based on the indicator value
protected override void OnBarUpdate()
{
   if (Value[0] > 70)
   {
     Lines[1].Brush = Brushes.Blue;
     Lines[1].Width = 3;
   }
   else
   {
     Lines[1].Brush = Brushes.Gray;
     Lines[1].Width = 1;
   }
}

```