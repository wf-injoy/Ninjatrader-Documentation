## [Definition](https://developer.ninjatrader.com/docs/desktop/isediting\#definition)

Determines if the anchor can be edited.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isediting\#property-value)

A bool value which when true determines if the chart anchor is currently in a state it can be edited. Default is false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isediting\#syntax)

`<chartanchor>.IsEditing`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isediting\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
    if (DrawingState == DrawingState.Building)
    {
        // if drawing tool is currently editing, update to current mouse point
        if (MyAnchor.IsEditing)
        {
            MyAnchor.UpdateFromPoint(point, chartControl, chartScale);

            //set the anchor to disable editing when done updating
            MyAnchor.IsEditing = false;
        }
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isediting\#definition)

Determines if the anchor can be edited.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isediting\#property-value)

A bool value which when true determines if the chart anchor is currently in a state it can be edited. Default is false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isediting\#syntax)

`<chartanchor>.IsEditing`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isediting\#examples)

```jsx-150469391 csharp
public override void OnMouseDown(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, Point point)
{
    if (DrawingState == DrawingState.Building)
    {
        // if drawing tool is currently editing, update to current mouse point
        if (MyAnchor.IsEditing)
        {
            MyAnchor.UpdateFromPoint(point, chartControl, chartScale);

            //set the anchor to disable editing when done updating
            MyAnchor.IsEditing = false;
        }
    }
}

```