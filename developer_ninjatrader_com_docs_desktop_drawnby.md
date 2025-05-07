## [Definition](https://developer.ninjatrader.com/docs/desktop/drawnby\#definition)

Represents the **NinjaScript** object which created the drawing object.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawnby\#property-value)

The **NinjaScript** object which created the drawing tool; this value will be null if drawn by a user.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawnby\#syntax)

`DrawnBy`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawnby\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // if the drawing tool was not created by a user,
    // print the name of the object that it was created
    if(!IsUserDrawn)
        Print(DrawnBy.Name);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawnby\#definition)

Represents the **NinjaScript** object which created the drawing object.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawnby\#property-value)

The **NinjaScript** object which created the drawing tool; this value will be null if drawn by a user.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawnby\#syntax)

`DrawnBy`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawnby\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // if the drawing tool was not created by a user,
    // print the name of the object that it was created
    if(!IsUserDrawn)
        Print(DrawnBy.Name);
}

```