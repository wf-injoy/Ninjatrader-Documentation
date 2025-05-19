## [Definition](https://developer.ninjatrader.com/docs/desktop/rectangle\#definition)

Represents an interface that exposes information regarding a Rectangle **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/rectangle\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An **IDrawingTool's ChartAnchor** representing the starting point of the drawing object |
| EndAnchor | An **IDrawingTool's ChartAnchor** representing the end point of the drawing object |
| AreaBrush | A **Brush** object representing the fill color of the draw object |
| AreaOpacity | An **int** value representing the opacity of the area color |
| OutlineStroke | The **Stroke** object used to draw the object's outline |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rectangle\#examples)

```jsx-150469391 csharp
// Instantiate a Rectangle object
Rectangle myRec = Draw.Rectangle(this, "tag1", 10, Low[10] - TickSize, 5, High[5] + TickSize, Brushes.Blue);

// Set the object's AreaBrush to Blue
myRec.AreaBrush = Brushes.Blue;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/rectangle\#definition)

Represents an interface that exposes information regarding a Rectangle **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/rectangle\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An **IDrawingTool's ChartAnchor** representing the starting point of the drawing object |
| EndAnchor | An **IDrawingTool's ChartAnchor** representing the end point of the drawing object |
| AreaBrush | A **Brush** object representing the fill color of the draw object |
| AreaOpacity | An **int** value representing the opacity of the area color |
| OutlineStroke | The **Stroke** object used to draw the object's outline |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rectangle\#examples)

```jsx-150469391 csharp
// Instantiate a Rectangle object
Rectangle myRec = Draw.Rectangle(this, "tag1", 10, Low[10] - TickSize, 5, High[5] + TickSize, Brushes.Blue);

// Set the object's AreaBrush to Blue
myRec.AreaBrush = Brushes.Blue;

```