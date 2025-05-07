## [Definition](https://developer.ninjatrader.com/docs/desktop/chartobjects\#definition)

A collection of objects configured on the chart panel.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartobjects\#property-value)

An **IList** of **Gui.NinjaScript.IChartObject** instances containing references to the objects configured on the panel.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartobjects\#syntax)

`ChartPanel.ChartObjects`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartobjects\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);

    IList<Gui.NinjaScript.IChartObject> myObjects = ChartPanel.ChartObjects;

    foreach (Gui.NinjaScript.IChartObject thisObject in myObjects)
    {
        Print(String.Format("{0} is of type {1}", thisObject.Name, thisObject.GetType()));
    }
}

```

The image below shows the output of the code example above, while applied in a chart panel with three objects.

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartobjects\#definition)

A collection of objects configured on the chart panel.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartobjects\#property-value)

An **IList** of **Gui.NinjaScript.IChartObject** instances containing references to the objects configured on the panel.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartobjects\#syntax)

`ChartPanel.ChartObjects`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartobjects\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    base.OnRender(chartControl, chartScale);

    IList<Gui.NinjaScript.IChartObject> myObjects = ChartPanel.ChartObjects;

    foreach (Gui.NinjaScript.IChartObject thisObject in myObjects)
    {
        Print(String.Format("{0} is of type {1}", thisObject.Name, thisObject.GetType()));
    }
}

```

The image below shows the output of the code example above, while applied in a chart panel with three objects.