## [Definition](https://developer.ninjatrader.com/docs/desktop/barsperiods\#definition)

Holds an array of BarsPeriod objects synchronized to the number of unique Bars objects held within the parent NinjaScript object. If a NinjaScript object holds two Bars series, then BarsPeriods will hold two BarsPeriod objects.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsperiods\#property-value)

An array of [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) objects.

## Warning

This property should NOT be accessed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached State.DataLoaded

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsperiods\#syntax)

`BarsPeriods[int barSeriesIndex]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsperiods\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the strategy and is automatically assigned
         // a Bars object index of 1 since the original data the strategy is ran on,
         // set by the UI, takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Print out 5, the value of the secondary bars object
     if (BarsInProgress == 1)
         Print(BarsPeriods[1].Value);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/barsperiods\#definition)

Holds an array of BarsPeriod objects synchronized to the number of unique Bars objects held within the parent NinjaScript object. If a NinjaScript object holds two Bars series, then BarsPeriods will hold two BarsPeriod objects.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsperiods\#property-value)

An array of [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) objects.

## Warning

This property should NOT be accessed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached State.DataLoaded

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsperiods\#syntax)

`BarsPeriods[int barSeriesIndex]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsperiods\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the strategy and is automatically assigned
         // a Bars object index of 1 since the original data the strategy is ran on,
         // set by the UI, takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Print out 5, the value of the secondary bars object
     if (BarsInProgress == 1)
         Print(BarsPeriods[1].Value);
}

```