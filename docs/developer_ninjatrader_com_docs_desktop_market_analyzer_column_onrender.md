## [Definition](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#definition)

Used to draw custom content to a Market Analyzer Column, such as a graph.

This method is called during the following conditions:

- The Market Analyzer is scrolled
- The user changes the Market Analyzer's properties through the Properties menu
- The Market Analyzer first loads (e.g. restoring from a workspace)
- The height / width of the Market Analyzer window changes
- A user re-sizes the content area by dragging the splitter between the columns

## Note

While similar to a Chart Indicator's **OnRender()** method, the Market Analyzer Column uses the **WPF Drawing Context** class, rather than the **SharpDX** library used for **chart rendering**. Concepts between these two methods are guaranteed to be different.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#syntax)

You must override the method in your Market Analyzer column with the following syntax:

`protected override void OnRender(DrawingContext dc, System.Windows.Size renderSize) {  }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#method-parameters)

| Parameter | Description |
| --- | --- |
| **dc** | The **drawing context** for the column |
| **renderSize** | The rendering size for the column |

## Note

In order to force **OnRender()** to be called under a specific condition, call the **OnPropertyChanged()** method which will force the entire column to repaint. This approach should be used instead of calling **OnRender()** directly.

## [Examples](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#examples)

```jsx-150469391 csharp
protected override void OnRender(DrawingContext dc, System.Windows.Size renderSize)
{
   // Rendering logic for our Market Analyzer column
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#definition)

Used to draw custom content to a Market Analyzer Column, such as a graph.

This method is called during the following conditions:

- The Market Analyzer is scrolled
- The user changes the Market Analyzer's properties through the Properties menu
- The Market Analyzer first loads (e.g. restoring from a workspace)
- The height / width of the Market Analyzer window changes
- A user re-sizes the content area by dragging the splitter between the columns

## Note

While similar to a Chart Indicator's **OnRender()** method, the Market Analyzer Column uses the **WPF Drawing Context** class, rather than the **SharpDX** library used for **chart rendering**. Concepts between these two methods are guaranteed to be different.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#syntax)

You must override the method in your Market Analyzer column with the following syntax:

`protected override void OnRender(DrawingContext dc, System.Windows.Size renderSize) {  }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#method-parameters)

| Parameter | Description |
| --- | --- |
| **dc** | The **drawing context** for the column |
| **renderSize** | The rendering size for the column |

## Note

In order to force **OnRender()** to be called under a specific condition, call the **OnPropertyChanged()** method which will force the entire column to repaint. This approach should be used instead of calling **OnRender()** directly.

## [Examples](https://developer.ninjatrader.com/docs/desktop/market_analyzer_column_onrender\#examples)

```jsx-150469391 csharp
protected override void OnRender(DrawingContext dc, System.Windows.Size renderSize)
{
   // Rendering logic for our Market Analyzer column
}

```