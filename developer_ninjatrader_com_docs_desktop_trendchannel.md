## [Definition](https://developer.ninjatrader.com/docs/desktop/trendchannel\#definition)

Represents an interface that exposes information regarding a Trend Channel [IDrawingTool](https://developer.ninjatrader.com/docs/desktop/idrawingtool).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/trendchannel\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| TrendStartAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the starting point of the drawing object |
| TrendEndAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the end point of the drawing object |
| ParallelStartAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the starting point of the second line used in the trend channel |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |

## [Example](https://developer.ninjatrader.com/docs/desktop/trendchannel\#example)

```jsx-150469391 csharp
// Instantiate a TrendChannel object
TrendChannel myTC = Draw.TrendChannel(this, "tag1", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);

// Increase the y-axis position of the object's TrendEndAnchor
myTC.TrendEndAnchor.Price += 15;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/trendchannel\#definition)

Represents an interface that exposes information regarding a Trend Channel [IDrawingTool](https://developer.ninjatrader.com/docs/desktop/idrawingtool).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/trendchannel\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| TrendStartAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the starting point of the drawing object |
| TrendEndAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the end point of the drawing object |
| ParallelStartAnchor | An [IDrawingTool's ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) representing the starting point of the second line used in the trend channel |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |

## [Example](https://developer.ninjatrader.com/docs/desktop/trendchannel\#example)

```jsx-150469391 csharp
// Instantiate a TrendChannel object
TrendChannel myTC = Draw.TrendChannel(this, "tag1", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);

// Increase the y-axis position of the object's TrendEndAnchor
myTC.TrendEndAnchor.Price += 15;

```