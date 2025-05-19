## [Definition](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#definition)

Represents an interface that exposes information regarding a Fibonacci Retracements **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An IDrawingTool's ChartAnchor representing the starting point of the drawing object |
| EndAnchor | An IDrawingTool's ChartAnchor representing the end point of the drawing object |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |
| TextLocation | An enum determining the text location; can be set to **TextLocation.Off** to remove text |
| IsExtendedLinesLeft | A bool value determining if the draw object should draw lines to the far left side of the screen |
| IsExtendedLinesRight | A bool value determining if the draw object should draw lines to the far right side of the screen |

## [Examples](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#examples)

```jsx-150469391 csharp
// Instantiate a FibonacciRetracements object
FibonacciRetracements myFibRet = Draw.FibonacciRetracements(this, "tag1", true, 10, Low[10], 0, High[0]);

// Set the object's lines to extend to the right
myFibRet.IsExtendedLinesRight = true;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#definition)

Represents an interface that exposes information regarding a Fibonacci Retracements **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An IDrawingTool's ChartAnchor representing the starting point of the drawing object |
| EndAnchor | An IDrawingTool's ChartAnchor representing the end point of the drawing object |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |
| TextLocation | An enum determining the text location; can be set to **TextLocation.Off** to remove text |
| IsExtendedLinesLeft | A bool value determining if the draw object should draw lines to the far left side of the screen |
| IsExtendedLinesRight | A bool value determining if the draw object should draw lines to the far right side of the screen |

## [Examples](https://developer.ninjatrader.com/docs/desktop/fibonacciretracements\#examples)

```jsx-150469391 csharp
// Instantiate a FibonacciRetracements object
FibonacciRetracements myFibRet = Draw.FibonacciRetracements(this, "tag1", true, 10, Low[10], 0, High[0]);

// Set the object's lines to extend to the right
myFibRet.IsExtendedLinesRight = true;

```