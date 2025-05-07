## [Definition](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#definition)

An event driven method which is called while the chart scale is being updated. This method is used to determine the highest and lowest value that can be used for the chart scale. It is only called when the chart object is either set to **IsAutoScale** while there are multiple charts objects rendered or only a single object would be rendered on the chart.

## Note

The indexer used to look up a **Series `<t>`** value through **barsAgo** is NOT guaranteed to be in sync when the **OnCalculateMinMax()** method is called. You will need to use **GetValueAt()** to obtain a historical value at a specified absolute index.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#syntax)

You must override the method in your NinjaScript object with the following syntax:

`public override void OnCalculateMinMax()`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#method-parameters)

This method does not accept any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name       = "Example Indicator";
        IsOverlay   = true;

        // set this to true to ensure CalculateMinMix() is called
        IsAutoScale = true;
    }
}

public override void OnCalculateMinMax()
{
    // make sure to always start fresh values to calculate new min/max values
    double tmpMin = double.MaxValue;
    double tmpMax = double.MinValue;

    // For performance optimization, only loop through what is viewable on the chart
    for (int index = ChartBars.FromIndex; index <= ChartBars.ToIndex; index++)
    {
        // since using Close[0] is not guaranteed to be in sync
        // retrieve "Close" value at the current viewable range index
        double plotValue = Close.GetValueAt(index);

        // return min/max of close value
        tmpMin = Math.Min(tmpMin, plotValue);
        tmpMax = Math.Max(tmpMax, plotValue);
    }

    // Finally, set the minimum and maximum Y-Axis values to +/- 50 ticks from the primary close value
    MinValue = tmpMin - 50 * TickSize;
    MaxValue = tmpMax + 50 * TickSize;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#definition)

An event driven method which is called while the chart scale is being updated. This method is used to determine the highest and lowest value that can be used for the chart scale. It is only called when the chart object is either set to **IsAutoScale** while there are multiple charts objects rendered or only a single object would be rendered on the chart.

## Note

The indexer used to look up a **Series `<t>`** value through **barsAgo** is NOT guaranteed to be in sync when the **OnCalculateMinMax()** method is called. You will need to use **GetValueAt()** to obtain a historical value at a specified absolute index.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#syntax)

You must override the method in your NinjaScript object with the following syntax:

`public override void OnCalculateMinMax()`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#method-parameters)

This method does not accept any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name       = "Example Indicator";
        IsOverlay   = true;

        // set this to true to ensure CalculateMinMix() is called
        IsAutoScale = true;
    }
}

public override void OnCalculateMinMax()
{
    // make sure to always start fresh values to calculate new min/max values
    double tmpMin = double.MaxValue;
    double tmpMax = double.MinValue;

    // For performance optimization, only loop through what is viewable on the chart
    for (int index = ChartBars.FromIndex; index <= ChartBars.ToIndex; index++)
    {
        // since using Close[0] is not guaranteed to be in sync
        // retrieve "Close" value at the current viewable range index
        double plotValue = Close.GetValueAt(index);

        // return min/max of close value
        tmpMin = Math.Min(tmpMin, plotValue);
        tmpMax = Math.Max(tmpMax, plotValue);
    }

    // Finally, set the minimum and maximum Y-Axis values to +/- 50 ticks from the primary close value
    MinValue = tmpMin - 50 * TickSize;
    MaxValue = tmpMax + 50 * TickSize;
}

```