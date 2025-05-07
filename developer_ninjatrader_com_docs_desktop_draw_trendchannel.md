## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#definition)

Draws a trend channel.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#method-return-value)

A **[TrendChannel](https://developer.ninjatrader.com/docs/desktop/trendchannel)** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#syntax)

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, bool isGlobal, string templateName)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, bool isGlobal, string templateName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#parameters)

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
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#examples)

```jsx-150469391 csharp
// Draws a trend channel
Draw.TrendChannel(this, "tag1", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#definition)

Draws a trend channel.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#method-return-value)

A **[TrendChannel](https://developer.ninjatrader.com/docs/desktop/trendchannel)** object that represents the draw object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#syntax)

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, int anchor1BarsAgo, double anchor1Y, int anchor2BarsAgo, double anchor2Y, int anchor3BarsAgo, double anchor3Y, bool isGlobal, string templateName)`

`Draw.TrendChannel(NinjaScriptBase owner, string tag, bool isAutoScale, DateTime anchor1Time, double anchor1Y, DateTime anchor2Time, double anchor2Y, DateTime anchor3Time, double anchor3Y, bool isGlobal, string templateName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#parameters)

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
| isGlobal | Determines if the draw object will be global across all charts which match the instrument. |
| templateName | The name of the drawing tool template the object will use to determine various visual properties (empty string could be used to just use the UI default visuals instead). |

## [Examples](https://developer.ninjatrader.com/docs/desktop/draw_trendchannel\#examples)

```jsx-150469391 csharp
// Draws a trend channel
Draw.TrendChannel(this, "tag1", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);

```