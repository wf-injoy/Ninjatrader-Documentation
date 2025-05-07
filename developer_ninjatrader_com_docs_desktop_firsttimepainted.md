## [Definition](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#definition)

Indicates a **DateTime** value of the first bar painted on the chart.

**FirstTimePainted** provides the timestamp of the first bar, NOT the time at which the bar was painted. For example, if a chart was opened and historical bars drawn on August 2nd at 5:00 pm, but the first bar on the chart is painted at a time-axis value of July 31st at 1:00 am, then **FirstTimePainted** will return the July 31st date and time.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#property-value)

A **DateTime** object containing information on the timestamp of the first bar of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#syntax)

`<chartcontrol>.FirstTimePainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Draw text to display the first timestamp of a bar on the chart
    Draw.Text(this, "firstTimeText", String.Format("The first bar of {0} is drawn at {1}", Instrument.MasterInstrument.Name, chartControl.FirstTimePainted), 1, High[0],Brushes.Black);
}

```

In the image below, **FirstTimePainted** reveals that the first painted slot corresponds to 8/12/17 at 10:40:00 AM.

## [Definition](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#definition)

Indicates a **DateTime** value of the first bar painted on the chart.

**FirstTimePainted** provides the timestamp of the first bar, NOT the time at which the bar was painted. For example, if a chart was opened and historical bars drawn on August 2nd at 5:00 pm, but the first bar on the chart is painted at a time-axis value of July 31st at 1:00 am, then **FirstTimePainted** will return the July 31st date and time.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#property-value)

A **DateTime** object containing information on the timestamp of the first bar of the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#syntax)

`<chartcontrol>.FirstTimePainted`

## [Examples](https://developer.ninjatrader.com/docs/desktop/firsttimepainted\#examples)

```jsx-150469391 csharp
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
    // Draw text to display the first timestamp of a bar on the chart
    Draw.Text(this, "firstTimeText", String.Format("The first bar of {0} is drawn at {1}", Instrument.MasterInstrument.Name, chartControl.FirstTimePainted), 1, High[0],Brushes.Black);
}

```

In the image below, **FirstTimePainted** reveals that the first painted slot corresponds to 8/12/17 at 10:40:00 AM.