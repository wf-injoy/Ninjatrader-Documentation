## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#definition)

Draws an Andrew's Pitchfork.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#method-return-value)

An **[AndrewsPitchfork](https://developer.ninjatrader.com/docs/desktop/andrewspitchfork)** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#syntax)

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, Brush brush, DashStyleHelper dashStyle, int width)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, Brush brush, DashStyleHelper dashStyle, int width)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, bool isGlobal, string templateName)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, bool isGlobal, string templateName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#parameters)

| owner | The hosting **NinjaScript** object which is calling the draw method. Typically will be the object which is calling the draw method (e.g., "this"). |
| tag | A user defined unique id used to reference the draw object. For example, if you pass in a value of "myTag", each time this tag is used, the same draw object is modified. If unique tags are used each time, a new draw object will be created each time. |
| isAutoScale | Determines if the draw object will be included in the y-axis scale. |
| anchor1BarsAgo | The number of bars ago (x value) of the 1st anchor point. |
| anchor1Time | The time of the 1st anchor point. |
| anchor1Y | The y value of the 1st anchor point. |
| anchor2BarsAgo | The number of bars ago (x value) of the 2nd anchor point. |
| anchor2Time | The time of the 2nd anchor point. |
| anchor2Y | The y value of the 2nd anchor point. |
| anchor3BarsAgo | The number of bars ago (x value) of the 3rd anchor point. |
| anchor3Time | The time of the 3rd anchor point. |
| anchor3Y | The y value of the 3rd anchor point. |
| brush | The brush used to color draw object ( [reference](https://developer.ninjatrader.com/docs/desktop/brushes)). |
| dashStyle | Possible values include:<br>- **DashStyleHelper.Dash**,<br>- **DashStyleHelper.DashDot**,<br>- **DashStyleHelper.DashDotDot**,<br>- **DashStyleHelper.Dot**,<br>- **DashStyleHelper.Solid**. |
| width | The width of the draw object. |
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## Note

Drawing objects with y values very far off the visible canvas can lead to performance hits. Fancier DashStyles like **DashDotDot** will also require more resources than simple DashStyles like **Solid**.

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#examples)

```jsx-150469391 csharp
// Draws an Andrew's Pitchfork
Draw.AndrewsPitchfork(this, "tag1", true, 4, Low[4], 3, High[3], 1, Low[1], Brushes.Blue, DashStyleHelper.Solid, 3);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#definition)

Draws an Andrew's Pitchfork.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#method-return-value)

An **[AndrewsPitchfork](https://developer.ninjatrader.com/docs/desktop/andrewspitchfork)** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#syntax)

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, Brush brush, DashStyleHelper dashStyle, int width)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, Brush brush, DashStyleHelper dashStyle, int width)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, bool isGlobal, string templateName)`

`Draw.AndrewsPitchfork(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, bool isGlobal, string templateName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#parameters)

| owner | The hosting **NinjaScript** object which is calling the draw method. Typically will be the object which is calling the draw method (e.g., "this"). |
| tag | A user defined unique id used to reference the draw object. For example, if you pass in a value of "myTag", each time this tag is used, the same draw object is modified. If unique tags are used each time, a new draw object will be created each time. |
| isAutoScale | Determines if the draw object will be included in the y-axis scale. |
| anchor1BarsAgo | The number of bars ago (x value) of the 1st anchor point. |
| anchor1Time | The time of the 1st anchor point. |
| anchor1Y | The y value of the 1st anchor point. |
| anchor2BarsAgo | The number of bars ago (x value) of the 2nd anchor point. |
| anchor2Time | The time of the 2nd anchor point. |
| anchor2Y | The y value of the 2nd anchor point. |
| anchor3BarsAgo | The number of bars ago (x value) of the 3rd anchor point. |
| anchor3Time | The time of the 3rd anchor point. |
| anchor3Y | The y value of the 3rd anchor point. |
| brush | The brush used to color draw object ( [reference](https://developer.ninjatrader.com/docs/desktop/brushes)). |
| dashStyle | Possible values include:<br>- **DashStyleHelper.Dash**,<br>- **DashStyleHelper.DashDot**,<br>- **DashStyleHelper.DashDotDot**,<br>- **DashStyleHelper.Dot**,<br>- **DashStyleHelper.Solid**. |
| width | The width of the draw object. |
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## Note

Drawing objects with y values very far off the visible canvas can lead to performance hits. Fancier DashStyles like **DashDotDot** will also require more resources than simple DashStyles like **Solid**.

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_andrewspitchfork\#examples)

```jsx-150469391 csharp
// Draws an Andrew's Pitchfork
Draw.AndrewsPitchfork(this, "tag1", true, 4, Low[4], 3, High[3], 1, Low[1], Brushes.Blue, DashStyleHelper.Solid, 3);

```