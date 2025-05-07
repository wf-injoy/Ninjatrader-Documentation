## [Definition](https://developer.ninjatrader.com/docs/desktop/drawingstate\#definition)

Represents the current state of the drawing tool to perform various actions, such as building, editing, or moving.

## [Property Values](https://developer.ninjatrader.com/docs/desktop/drawingstate\#property-values)

An enum representing the current state of the drawing tool. Possible values are:

| **DrawingState.Building** | The initial state when a drawing tool is first being drawn, allowing for the anchors to be set for the drawing. |
| **DrawingState.Editing** | Allows for changing the values of any of the drawing tools anchors |
| **DrawingState.Normal** | The drawing tool is normal on the chart and is not in a state to allow for changes. |
| **DrawingState.Moving** | The entire drawing tool to be moved by a user. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawingstate\#syntax)

`DrawingState`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawingstate\#examples)

```jsx-150469391 csharp

public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   switch(DrawingState)
   {
     case DrawingState.Normal:
         DrawingState = DrawingState.Editing; // set state to allow editing
         break;
     case DrawingState.Editing:
         // do your edits here
         break;
     case DrawingState.Moving:
         return; // don't allow move when editing
   }

}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawingstate\#definition)

Represents the current state of the drawing tool to perform various actions, such as building, editing, or moving.

## [Property Values](https://developer.ninjatrader.com/docs/desktop/drawingstate\#property-values)

An enum representing the current state of the drawing tool. Possible values are:

| **DrawingState.Building** | The initial state when a drawing tool is first being drawn, allowing for the anchors to be set for the drawing. |
| **DrawingState.Editing** | Allows for changing the values of any of the drawing tools anchors |
| **DrawingState.Normal** | The drawing tool is normal on the chart and is not in a state to allow for changes. |
| **DrawingState.Moving** | The entire drawing tool to be moved by a user. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawingstate\#syntax)

`DrawingState`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawingstate\#examples)

```jsx-150469391 csharp

public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
   switch(DrawingState)
   {
     case DrawingState.Normal:
         DrawingState = DrawingState.Editing; // set state to allow editing
         break;
     case DrawingState.Editing:
         // do your edits here
         break;
     case DrawingState.Moving:
         return; // don't allow move when editing
   }

}

```