## [Definition](https://developer.ninjatrader.com/docs/desktop/textfixed\#definition)

Represents an interface that exposes information regarding a Text Fixed **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/textfixed\#methods-and-properties)

| Anchor | YPixelOffset | Alignment | AreaOpacity | AreaBrush | DisplayText | TextBrush | Font | OutlineStroke | TextPosition |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| An **IDrawingTool's ChartAnchor** representing the point of the drawing object | An **int** value representing the offset value in pixels from within the text box area | Possible values are:<br>**TextAlignment.Center**<br>**TextAlignment.Far**<br>**TextAlignment.Near**<br>**TextAlignment.Justify**<br>( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment%28v=vs.110%29.aspx)) | An **int** value representing the opacity of the area color | A **Brush** class representing the fill color of the text box | A **string** value representing the text to be drawn | A **Brush** class representing the color of the text | A **Font** object representing the font for the text | The **Stroke** object used to outline the text box | Possible values are:<br>**TextPosition.BottomLeft**<br>**TextPosition.BottomRight**<br>**TextPosition.Center**<br>**TextPosition.TopLeft**<br>**TextPosition.TopRight** |

## [Examples](https://developer.ninjatrader.com/docs/desktop/textfixed\#examples)

```jsx-150469391 csharp
// Instantiate a TextFixed object
TextFixed myTF = Draw.TextFixed(this, "tag1", "Text to draw", TextPosition.TopRight);

// Change the object's TextPosition
myTF.TextPosition = TextPosition.Center;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/textfixed\#definition)

Represents an interface that exposes information regarding a Text Fixed **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/textfixed\#methods-and-properties)

| Anchor | YPixelOffset | Alignment | AreaOpacity | AreaBrush | DisplayText | TextBrush | Font | OutlineStroke | TextPosition |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| An **IDrawingTool's ChartAnchor** representing the point of the drawing object | An **int** value representing the offset value in pixels from within the text box area | Possible values are:<br>**TextAlignment.Center**<br>**TextAlignment.Far**<br>**TextAlignment.Near**<br>**TextAlignment.Justify**<br>( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment%28v=vs.110%29.aspx)) | An **int** value representing the opacity of the area color | A **Brush** class representing the fill color of the text box | A **string** value representing the text to be drawn | A **Brush** class representing the color of the text | A **Font** object representing the font for the text | The **Stroke** object used to outline the text box | Possible values are:<br>**TextPosition.BottomLeft**<br>**TextPosition.BottomRight**<br>**TextPosition.Center**<br>**TextPosition.TopLeft**<br>**TextPosition.TopRight** |

## [Examples](https://developer.ninjatrader.com/docs/desktop/textfixed\#examples)

```jsx-150469391 csharp
// Instantiate a TextFixed object
TextFixed myTF = Draw.TextFixed(this, "tag1", "Text to draw", TextPosition.TopRight);

// Change the object's TextPosition
myTF.TextPosition = TextPosition.Center;

```