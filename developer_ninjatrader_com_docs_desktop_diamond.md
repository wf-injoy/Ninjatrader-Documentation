## [Definition](https://developer.ninjatrader.com/docs/desktop/diamond\#definition)

Represents an interface that exposes information regarding a Diamond **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/diamond\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| Anchor | An **IDrawingTool's ChartAnchor** representing the point of the drawing object |
| AreaBrush | A **Brush** object representing the fill color of the draw object |
| OutlineBrush | A **Brush** object representing the color of the draw object's outline |

## [Examples](https://developer.ninjatrader.com/docs/desktop/diamond\#examples)

```jsx-150469391 csharp
// Instantiates a red diamond on the current bar 1 tick below the low
Diamond myDiamond = Draw.Diamond(this, "tag1", true, 0, Low[0] - TickSize, Brushes.Red);

// Set the area fill color to Red
myDiamond.AreaBrush = Brushes.Red;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/diamond\#definition)

Represents an interface that exposes information regarding a Diamond **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/diamond\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| Anchor | An **IDrawingTool's ChartAnchor** representing the point of the drawing object |
| AreaBrush | A **Brush** object representing the fill color of the draw object |
| OutlineBrush | A **Brush** object representing the color of the draw object's outline |

## [Examples](https://developer.ninjatrader.com/docs/desktop/diamond\#examples)

```jsx-150469391 csharp
// Instantiates a red diamond on the current bar 1 tick below the low
Diamond myDiamond = Draw.Diamond(this, "tag1", true, 0, Low[0] - TickSize, Brushes.Red);

// Set the area fill color to Red
myDiamond.AreaBrush = Brushes.Red;

```