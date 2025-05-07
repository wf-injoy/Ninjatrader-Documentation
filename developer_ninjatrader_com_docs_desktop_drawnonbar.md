## [Definition](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#definition)

Gets the current bar value that the chart anchor is drawn by a **NinjaScript** object. Please see the [Drawing](https://developer.ninjatrader.com/docs/desktop/drawing) section for more information.

## Note

This value will NOT work on manually drawn objects. This property is reserved for chart anchors which were drawn by another **NinjaScript** object (e.g., using a Draw method in an indicator). For manually drawn objects, please see the [SlotIndex](https://developer.ninjatrader.com/docs/desktop/barindex) property.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#property-value)

A int value that value which the current bar the chart anchor is drawn. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#syntax)

`<chartanchor>.DrawnOnBar`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#examples)

```jsx-150469391 csharp
// Places text if high is 2419 and prints what bar the text was drawn on
if (High[0] == 2419)
{
    Text myText = Draw.Text(this, @"Text " + CurrentBar, @"High is 2419" , 0, High[0]);
    Print("Text is on bar " + myText.Anchor.DrawnOnBar);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#definition)

Gets the current bar value that the chart anchor is drawn by a **NinjaScript** object. Please see the [Drawing](https://developer.ninjatrader.com/docs/desktop/drawing) section for more information.

## Note

This value will NOT work on manually drawn objects. This property is reserved for chart anchors which were drawn by another **NinjaScript** object (e.g., using a Draw method in an indicator). For manually drawn objects, please see the [SlotIndex](https://developer.ninjatrader.com/docs/desktop/barindex) property.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#property-value)

A int value that value which the current bar the chart anchor is drawn. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#syntax)

`<chartanchor>.DrawnOnBar`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawnonbar\#examples)

```jsx-150469391 csharp
// Places text if high is 2419 and prints what bar the text was drawn on
if (High[0] == 2419)
{
    Text myText = Draw.Text(this, @"Text " + CurrentBar, @"High is 2419" , 0, High[0]);
    Print("Text is on bar " + myText.Anchor.DrawnOnBar);
}

```