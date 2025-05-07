## [Definition](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#definition)

Represents an interface that exposes information regarding a Fibonacci Time Extensions **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An **IDrawingTool's ChartAnchor** representing the starting point of the drawing object |
| EndAnchor | An **IDrawingTool's ChartAnchor** representing the end point of the drawing object |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |
| IsTextDisplayed | A bool value determining if the draw object should display text on the chart. |
| IsExtendedLinesLeft | A bool value determining if the draw object should draw lines to the far left side of the screen |
| IsExtendedLinesRight | A bool value determining if the draw object should draw lines to the far right side of the screen |

## [Examples](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#examples)

```jsx-150469391 csharp
// Instantiate a FibonacciTimeExtensions object
FibonacciTimeExtensions myFibTime = Draw.FibonacciTimeExtensions(this, "tag1", false, 10, Low[10], 0, High[0]);

// Instantiate a new PriceLevel to be used in the step below
PriceLevel myLevel = new PriceLevel(99, Brushes.Black);

// Change the object's price level at index 3
myFibTime.PriceLevels[3] = myLevel;

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#definition)

Represents an interface that exposes information regarding a Fibonacci Time Extensions **IDrawingTool**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#methods-and-properties)

| Parameter | Description |
| --- | --- |
| StartAnchor | An **IDrawingTool's ChartAnchor** representing the starting point of the drawing object |
| EndAnchor | An **IDrawingTool's ChartAnchor** representing the end point of the drawing object |
| [PriceLevels](https://developer.ninjatrader.com/docs/desktop/pricelevels) | A collection of prices calculated by the drawing object |
| IsTextDisplayed | A bool value determining if the draw object should display text on the chart. |
| IsExtendedLinesLeft | A bool value determining if the draw object should draw lines to the far left side of the screen |
| IsExtendedLinesRight | A bool value determining if the draw object should draw lines to the far right side of the screen |

## [Examples](https://developer.ninjatrader.com/docs/desktop/fibonaccitimeextensions\#examples)

```jsx-150469391 csharp
// Instantiate a FibonacciTimeExtensions object
FibonacciTimeExtensions myFibTime = Draw.FibonacciTimeExtensions(this, "tag1", false, 10, Low[10], 0, High[0]);

// Instantiate a new PriceLevel to be used in the step below
PriceLevel myLevel = new PriceLevel(99, Brushes.Black);

// Change the object's price level at index 3
myFibTime.PriceLevels[3] = myLevel;

```