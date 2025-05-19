## [Definition](https://developer.ninjatrader.com/docs/desktop/text\#definition)

Represents an interface that exposes information regarding a Text [IDrawingTool](https://developer.ninjatrader.com/docs/desktop/idrawingtool).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/text\#methods-and-properties)

| Anchor | An [IDrawingTool's](https://developer.ninjatrader.com/docs/desktop/idrawingtool)'s **ChartAnchor** representing the point of the drawing object |
| --- | --- |
| YPixelOffset | An int value representing the offset value in pixels from within the text box area |
| Alignment | Possible values are:<br>- TextAlignment.Center<br>- TextAlignment.Left<br>- TextAlignment.Right<br>- TextAlignment.Justify [MSDN reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment(v=vs.110).aspx) |
| AreaOpacity | An int value representing the opacity of the area color |
| AreaBrush | A [Brush](http://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) class representing the fill color of the text box |
| Text | A string value representing the text to be drawn |
| TextBrush | A [Brush](http://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) class representing the color of the text |
| Font | A [Font](http://msdn.microsoft.com/en-us/library/system.drawing.font_members(v=vs.90).aspx) object representing the font for the text |
| OutlineStroke | The Stroke object used to outline the text box |

## [Examples](https://developer.ninjatrader.com/docs/desktop/text\#examples)

```jsx-150469391 csharp
// Instantiate a Text object
Text myText = Draw.Text(this, "tag1", "Text to draw", 10, High[10] + (5 * TickSize), Brushes.Black);

// Change the object's DisplayText
myText.DisplayText = "New Display Text";

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/text\#definition)

Represents an interface that exposes information regarding a Text [IDrawingTool](https://developer.ninjatrader.com/docs/desktop/idrawingtool).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/text\#methods-and-properties)

| Anchor | An [IDrawingTool's](https://developer.ninjatrader.com/docs/desktop/idrawingtool)'s **ChartAnchor** representing the point of the drawing object |
| --- | --- |
| YPixelOffset | An int value representing the offset value in pixels from within the text box area |
| Alignment | Possible values are:<br>- TextAlignment.Center<br>- TextAlignment.Left<br>- TextAlignment.Right<br>- TextAlignment.Justify [MSDN reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment(v=vs.110).aspx) |
| AreaOpacity | An int value representing the opacity of the area color |
| AreaBrush | A [Brush](http://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) class representing the fill color of the text box |
| Text | A string value representing the text to be drawn |
| TextBrush | A [Brush](http://msdn.microsoft.com/en-us/library/system.windows.media.brush(v=vs.110).aspx) class representing the color of the text |
| Font | A [Font](http://msdn.microsoft.com/en-us/library/system.drawing.font_members(v=vs.90).aspx) object representing the font for the text |
| OutlineStroke | The Stroke object used to outline the text box |

## [Examples](https://developer.ninjatrader.com/docs/desktop/text\#examples)

```jsx-150469391 csharp
// Instantiate a Text object
Text myText = Draw.Text(this, "tag1", "Text to draw", 10, High[10] + (5 * TickSize), Brushes.Black);

// Change the object's DisplayText
myText.DisplayText = "New Display Text";

```