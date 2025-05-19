## [Definition](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#definition)

Indicates the type of bar spacing used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#property-value)

An enum representing one of the values below:

| EquidistantSingle | Indicates Equidistant Bar Spacing is used, and only one Bars object exists on the chart |
| EquidistantMulti | Indicates Equidistant Bar Spacing is used, and more than one Bars objects exist on the chart |
| TimeBased | Indicates Time-Based bar spacing is used |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#syntax)

`chartcontrol.BarSpacingType`

## [Example](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Print the type of bar spacing used on the chart
   Print(chartControl.BarSpacingType);
}

```

Based on the image below, BarSpacingType confirms that there are multiple Bars objects configured on the chart, and that the chart is set to Equidistant Bar Spacing:

## [Definition](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#definition)

Indicates the type of bar spacing used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#property-value)

An enum representing one of the values below:

| EquidistantSingle | Indicates Equidistant Bar Spacing is used, and only one Bars object exists on the chart |
| EquidistantMulti | Indicates Equidistant Bar Spacing is used, and more than one Bars objects exist on the chart |
| TimeBased | Indicates Time-Based bar spacing is used |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#syntax)

`chartcontrol.BarSpacingType`

## [Example](https://developer.ninjatrader.com/docs/desktop/barspacingtype\#example)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   // Print the type of bar spacing used on the chart
   Print(chartControl.BarSpacingType);
}

```

Based on the image below, BarSpacingType confirms that there are multiple Bars objects configured on the chart, and that the chart is set to Equidistant Bar Spacing: