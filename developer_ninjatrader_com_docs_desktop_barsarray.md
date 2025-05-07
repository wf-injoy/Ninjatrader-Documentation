## [Definition](https://developer.ninjatrader.com/docs/desktop/barsarray\#definition)

An array holding Bars objects that are added via the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method. BarsArray can be used as input for [indicator methods](https://developer.ninjatrader.com/docs/desktop/system_indicator_methods). This property is of primary value when working with [multi-time frame or multi-instrument scripts](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsarray\#property-value)

An array of [Bars](https://developer.ninjatrader.com/docs/desktop/bars) objects.

## Warning

This property should NOT be accessed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached **State.DataLoaded**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsarray\#syntax)

`BarsArray[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsarray\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "Examples Indicator";
    }
    else if (State == State.Configure)
    {
        // Add a 5 minute Bars object which is added to the BarArray
        // which will take index 1 since the primary Bars object of the strategy
        // will be index 0
        AddDataSeries(BarsPeriodType.Minute, 5);
    }
}

protected override void OnBarUpdate()
{
    // Ignore bar update events for the supplementary Bars object added above
    if (BarsInProgress == 1)
        return;

    // Pass in a Bars object as input for the simple moving average method
    // Evaluates if the 20 SMA of the primary Bars is greater than
    // the 20 SMA of the secondary Bars added above
    if (SMA(20)[0] > SMA(BarsArray[1], 20)[0])
        EnterLong();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/barsarray\#definition)

An array holding Bars objects that are added via the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method. BarsArray can be used as input for [indicator methods](https://developer.ninjatrader.com/docs/desktop/system_indicator_methods). This property is of primary value when working with [multi-time frame or multi-instrument scripts](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsarray\#property-value)

An array of [Bars](https://developer.ninjatrader.com/docs/desktop/bars) objects.

## Warning

This property should NOT be accessed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached **State.DataLoaded**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsarray\#syntax)

`BarsArray[int index]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsarray\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "Examples Indicator";
    }
    else if (State == State.Configure)
    {
        // Add a 5 minute Bars object which is added to the BarArray
        // which will take index 1 since the primary Bars object of the strategy
        // will be index 0
        AddDataSeries(BarsPeriodType.Minute, 5);
    }
}

protected override void OnBarUpdate()
{
    // Ignore bar update events for the supplementary Bars object added above
    if (BarsInProgress == 1)
        return;

    // Pass in a Bars object as input for the simple moving average method
    // Evaluates if the 20 SMA of the primary Bars is greater than
    // the 20 SMA of the secondary Bars added above
    if (SMA(20)[0] > SMA(BarsArray[1], 20)[0])
        EnterLong();
}

```