## [Definition](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#definition)

Indicates if the chart anchor was drawn by a **NinjaScript** object (such as an indicator or strategy).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#property-value)

A bool value which returns true if the object was drawn by another **NinjaScript** object; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#syntax)

`<chartanchor>.IsNinjaScriptDrawn`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#examples)

```jsx-150469391 csharp
//unlocks the NinjaScript drawn object and allows the user to modify the anchor, while the NinjaScript object still 'owns' the object
protected override void OnBarUpdate()
{
     foreach(IDrawingTool dt in DrawObjects)
         {
           DrawingTools.Line sampleLine = dt as DrawingTools.Line;

           if (sampleLine != null && sampleLine.StartAnchor.IsNinjaScriptDrawn)
           {
               sampleLine.IsLocked = false;
               Print(sampleLine.StartAnchor.ToString());
           }
         }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#definition)

Indicates if the chart anchor was drawn by a **NinjaScript** object (such as an indicator or strategy).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#property-value)

A bool value which returns true if the object was drawn by another **NinjaScript** object; otherwise false. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#syntax)

`<chartanchor>.IsNinjaScriptDrawn`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn\#examples)

```jsx-150469391 csharp
//unlocks the NinjaScript drawn object and allows the user to modify the anchor, while the NinjaScript object still 'owns' the object
protected override void OnBarUpdate()
{
     foreach(IDrawingTool dt in DrawObjects)
         {
           DrawingTools.Line sampleLine = dt as DrawingTools.Line;

           if (sampleLine != null && sampleLine.StartAnchor.IsNinjaScriptDrawn)
           {
               sampleLine.IsLocked = false;
               Print(sampleLine.StartAnchor.ToString());
           }
         }
}

```