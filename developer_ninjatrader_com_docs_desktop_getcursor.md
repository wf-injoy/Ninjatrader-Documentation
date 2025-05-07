## [Definition](https://developer.ninjatrader.com/docs/desktop/getcursor\#definition)

An event driven method which is called when a chart object is selected. This method can be used to change the cursor image used in various states.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcursor\#method-return-value)

This method returns a **Cursor** used to paint the mouse pointer.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcursor\#syntax)

You must override the method in your Drawing Tool with the following syntax:

`public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getcursor\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **point** | A Point in device pixels representing the current mouse cursor position |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcursor\#examples)

```jsx-150469391 csharp
public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
    switch (DrawingState)
    {
        //when drawing, display the cursor as a pen
        case DrawingState.Building:   return Cursors.Pen;

        // when moving, display a four-headed sizing cursor
        case DrawingState.Moving:   return Cursors.SizeAll;

        default: return Cursors.Pen;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getcursor\#definition)

An event driven method which is called when a chart object is selected. This method can be used to change the cursor image used in various states.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcursor\#method-return-value)

This method returns a **Cursor** used to paint the mouse pointer.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcursor\#syntax)

You must override the method in your Drawing Tool with the following syntax:

`public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getcursor\#method-parameters)

| **chartControl** | A [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol) representing the x-axis |
| **chartPanel** | A [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) representing the panel for the chart |
| **chartScale** | A [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) representing the y-axis |
| **point** | A Point in device pixels representing the current mouse cursor position |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcursor\#examples)

```jsx-150469391 csharp
public override Cursor GetCursor(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
    switch (DrawingState)
    {
        //when drawing, display the cursor as a pen
        case DrawingState.Building:   return Cursors.Pen;

        // when moving, display a four-headed sizing cursor
        case DrawingState.Moving:   return Cursors.SizeAll;

        default: return Cursors.Pen;
    }
}

```