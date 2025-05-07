## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_text\#definition)

Draws text.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_text\#method-return-value)

A **Text** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_text\#syntax)

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y)`

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y, Brush textBrush)`

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y, bool isGlobal, string templateName)`

`Draw.Text(NinjaScriptBase owner, string tag, bool isAutoScale, string text, int barsAgo, double y, int yPixelOffset, Brush textBrush, SimpleFont font, TextAlignment alignment, Brush outlineBrush, Brush areaBrush, int areaOpacity)`

`Draw.Text(NinjaScriptBase owner, string tag, bool isAutoScale, string text, DateTime time, double y, int yPixelOffset, Brush textBrush, SimpleFont font, TextAlignment alignment, Brush outlineBrush, Brush areaBrush, int areaOpacity)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_text\#parameters)

| owner | The hosting **NinjaScript** object which is calling the draw method. Typically will be the object which is calling the draw method (e.g., "this"). |
| tag | A user defined unique id used to reference the draw object. For example, if you pass in a value of "myTag", each time this tag is used, the same draw object is modified. If unique tags are used each time, a new draw object will be created each time. |
| isAutoScale | Determines if the draw object will be included in the y-axis scale. Default value is false. |
| text | The text you wish to draw. |
| barsAgo | The bar (x axis co-ordinate) where the draw object will be drawn. For example, a value of 10 would paint the draw object 10 bars back. |
| time | The time where the draw object will be drawn. |
| y | The y co-ordinate location the object will be drawn. |
| yPixelOffset | The offset value in pixels from within the text box area. |
| textBrush | The brush used to color the text of the draw object ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment%28v=vs.110%29.aspx)). |
| font | A **Simple Font** object. |
| alignment | **TextAlignment.Center**, **TextAlignment.Left**, **TextAlignment.Right**, **TextAlignment.Justify** ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment(v=vs.110).aspx)). |
| outlineBrush | The brush used to color the text box outline ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)). |
| areaBrush | The brush used to color the text box fill area ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)). |
| areaOpacity | Sets the level of transparency for the fill color. Valid values between 0 - 100. (0 = completely transparent, 100 = no opacity). |
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_text\#examples)

```jsx-150469391 csharp
// Draws text
Draw.Text(this, "tag1", "Text to draw", 10, 1000, Brushes.Black);

```

## Note

Tip: In some cases, it may be useful to pass in the **ChartControl.Properties** **TextFont** brush as well as the **LabelFont** **SimpleFont** object to render your custom text. This will help ensure that the text will be visible and match what a user has configured for their chart label display settings.

```jsx-150469391 csharp
// match the text brush to what the user has configured on their chart
Draw.Text(this, "tag1", "Text to draw", 10, 1000, ChartControl.Properties.ChartText);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_text\#definition)

Draws text.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_text\#method-return-value)

A **Text** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_text\#syntax)

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y)`

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y, Brush textBrush)`

`Draw.Text(NinjaScriptBase owner, string tag, string text, int barsAgo, double y, bool isGlobal, string templateName)`

`Draw.Text(NinjaScriptBase owner, string tag, bool isAutoScale, string text, int barsAgo, double y, int yPixelOffset, Brush textBrush, SimpleFont font, TextAlignment alignment, Brush outlineBrush, Brush areaBrush, int areaOpacity)`

`Draw.Text(NinjaScriptBase owner, string tag, bool isAutoScale, string text, DateTime time, double y, int yPixelOffset, Brush textBrush, SimpleFont font, TextAlignment alignment, Brush outlineBrush, Brush areaBrush, int areaOpacity)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_text\#parameters)

| owner | The hosting **NinjaScript** object which is calling the draw method. Typically will be the object which is calling the draw method (e.g., "this"). |
| tag | A user defined unique id used to reference the draw object. For example, if you pass in a value of "myTag", each time this tag is used, the same draw object is modified. If unique tags are used each time, a new draw object will be created each time. |
| isAutoScale | Determines if the draw object will be included in the y-axis scale. Default value is false. |
| text | The text you wish to draw. |
| barsAgo | The bar (x axis co-ordinate) where the draw object will be drawn. For example, a value of 10 would paint the draw object 10 bars back. |
| time | The time where the draw object will be drawn. |
| y | The y co-ordinate location the object will be drawn. |
| yPixelOffset | The offset value in pixels from within the text box area. |
| textBrush | The brush used to color the text of the draw object ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment%28v=vs.110%29.aspx)). |
| font | A **Simple Font** object. |
| alignment | **TextAlignment.Center**, **TextAlignment.Left**, **TextAlignment.Right**, **TextAlignment.Justify** ( [reference](https://msdn.microsoft.com/en-us/library/system.windows.textalignment(v=vs.110).aspx)). |
| outlineBrush | The brush used to color the text box outline ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)). |
| areaBrush | The brush used to color the text box fill area ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)). |
| areaOpacity | Sets the level of transparency for the fill color. Valid values between 0 - 100. (0 = completely transparent, 100 = no opacity). |
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_text\#examples)

```jsx-150469391 csharp
// Draws text
Draw.Text(this, "tag1", "Text to draw", 10, 1000, Brushes.Black);

```

## Note

Tip: In some cases, it may be useful to pass in the **ChartControl.Properties** **TextFont** brush as well as the **LabelFont** **SimpleFont** object to render your custom text. This will help ensure that the text will be visible and match what a user has configured for their chart label display settings.

```jsx-150469391 csharp
// match the text brush to what the user has configured on their chart
Draw.Text(this, "tag1", "Text to draw", 10, 1000, ChartControl.Properties.ChartText);

```