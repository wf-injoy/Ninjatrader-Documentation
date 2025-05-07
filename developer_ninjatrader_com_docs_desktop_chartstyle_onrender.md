## [Definition](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#definition)

An event driven method used to render content to a ChartStyle. The **OnRender()** method is called every time the chart values are updated. These updates are driven by incoming data to the chart bars or by a user manually interacting with the chart control or chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#syntax)

You must override the method in your ChartStyle with the following syntax:

`protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)  {  }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#method-parameters)

| **chartControl** | A ChartControl representing the x-axis |
| **chartScale** | A ChartScale representing the y-axis |
| **chartBars** | A ChartBars representing the Bars series for the chart |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)
{
    // Rendering logic for our chart style
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#definition)

An event driven method used to render content to a ChartStyle. The **OnRender()** method is called every time the chart values are updated. These updates are driven by incoming data to the chart bars or by a user manually interacting with the chart control or chart scale.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#syntax)

You must override the method in your ChartStyle with the following syntax:

`protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)  {  }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#method-parameters)

| **chartControl** | A ChartControl representing the x-axis |
| **chartScale** | A ChartScale representing the y-axis |
| **chartBars** | A ChartBars representing the Bars series for the chart |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartstyle_onrender\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale, ChartBars chartBars)
{
    // Rendering logic for our chart style
}

```