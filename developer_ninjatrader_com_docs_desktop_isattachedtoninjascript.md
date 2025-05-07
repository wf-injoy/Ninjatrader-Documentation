## [Definition](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#definition)

Indicates if the drawing tool is currently **attached to** a NinjaScript object (such an indicator or a strategy).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#property-value)

A bool value which when true if the drawing tool is attached to a NinjaScript object; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#syntax)

`IsAttachedToNinjaScript`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
    // do not interact if drawn by an indicator or strategy
    if (IsAttachedToNinjaScript)
        return;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#definition)

Indicates if the drawing tool is currently **attached to** a NinjaScript object (such an indicator or a strategy).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#property-value)

A bool value which when true if the drawing tool is attached to a NinjaScript object; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#syntax)

`IsAttachedToNinjaScript`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript\#examples)

```jsx-150469391 csharp
public override void OnMouseMove(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
    // do not interact if drawn by an indicator or strategy
    if (IsAttachedToNinjaScript)
        return;
}

```