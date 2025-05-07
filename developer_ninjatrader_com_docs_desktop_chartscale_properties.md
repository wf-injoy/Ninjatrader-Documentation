## [Definition](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#definition)

Represents a number of properties available to the Chart Scale which can be configured to change the appearance of the scale.

## Warning

These are UI properties which are designed to be set by a user. Attempting to modify these values through a custom script is NOT guaranteed to take effect.

## [Property Values](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#property-values)

| Property | Description |
| --- | --- |
| **YAxisRangeType** | An **YAxisRangeType** enum, possible values are:<br>- Automatic<br>- Fixed |
| **AutoScaleDateRangeType** | An **AutoScaleDateRangeType** enum, possible values are:<br>- ScreenDateRange<br>- EntireDateRangeSeriesOnly |
| **HorizontalGridlinesCalculation** | An **YAxisRangeType** enum, possible values are:<br>- Automatic<br>- Fixed |
| **HorizontalGridlinesIntervalType** | A **HorizontalGridlinesIntervalType** enum, possible values are:<br>- Ticks<br>- Points<br>- Pips |
| **HorizontalGridlinesInterval** | A **double** value representing the vertical interval of the horizontal axis |
| **AutoScaleMarginType** | An **AutoScaleMarginType** enum, possible values are:<br>- Percent<br>- Price |
| **AutoScaleMarginLower** | A **double** value representing the lowest margin used for the chart scale |
| **AutoScaleMarginUpper** | A **double** value representing the highest margin used for the chart scale |
| **YAxisScalingType** | An **YAxisScalingType** enum, possible values are:<br>- Linear<br>- Logarithmic |
| **FixedScaleMax** | A double representing the highest series value used for the chart scale when the scale is fixed |
| **FixedScaleMin** | A double representing the lowest series value used for the chart scale when the scale is fixed |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#syntax)

`<chartscale>.Properties`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    if (chartScale.Properties.YAxisScalingType == AxisScalingTypeLinear)
    {
        // do something
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#definition)

Represents a number of properties available to the Chart Scale which can be configured to change the appearance of the scale.

## Warning

These are UI properties which are designed to be set by a user. Attempting to modify these values through a custom script is NOT guaranteed to take effect.

## [Property Values](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#property-values)

| Property | Description |
| --- | --- |
| **YAxisRangeType** | An **YAxisRangeType** enum, possible values are:<br>- Automatic<br>- Fixed |
| **AutoScaleDateRangeType** | An **AutoScaleDateRangeType** enum, possible values are:<br>- ScreenDateRange<br>- EntireDateRangeSeriesOnly |
| **HorizontalGridlinesCalculation** | An **YAxisRangeType** enum, possible values are:<br>- Automatic<br>- Fixed |
| **HorizontalGridlinesIntervalType** | A **HorizontalGridlinesIntervalType** enum, possible values are:<br>- Ticks<br>- Points<br>- Pips |
| **HorizontalGridlinesInterval** | A **double** value representing the vertical interval of the horizontal axis |
| **AutoScaleMarginType** | An **AutoScaleMarginType** enum, possible values are:<br>- Percent<br>- Price |
| **AutoScaleMarginLower** | A **double** value representing the lowest margin used for the chart scale |
| **AutoScaleMarginUpper** | A **double** value representing the highest margin used for the chart scale |
| **YAxisScalingType** | An **YAxisScalingType** enum, possible values are:<br>- Linear<br>- Logarithmic |
| **FixedScaleMax** | A double representing the highest series value used for the chart scale when the scale is fixed |
| **FixedScaleMin** | A double representing the lowest series value used for the chart scale when the scale is fixed |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#syntax)

`<chartscale>.Properties`

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartscale_properties\#examples)

```jsx-150469391 csharp

protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    if (chartScale.Properties.YAxisScalingType == AxisScalingTypeLinear)
    {
        // do something
    }
}

```