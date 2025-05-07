## [Definition](https://developer.ninjatrader.com/docs/desktop/currentbars\#definition)

Holds an array of int values representing the number of the current bar in a Bars object. An **int** value is added to this array when calling the **[AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries)** method. Its purpose is to provide access to the **[CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar)** of all Bars objects in a multi-instrument or multi-time frame script.

## Note

In **[multi series](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments)** processing, the CurrentBars starting value will be -1 until all series have processed the first bar.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/currentbars\#property-value)

An array of int values.

## Warning

Warning: This property should NOT be accessed within the **[OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange)** method before the State has reached State.DataLoaded.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/currentbars\#syntax)

`CurrentBars[int barSeriesIndex]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/currentbars\#examples)

### Indicator ( **[BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot)**)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the script. It will automatically be assigned
         // a Bars object index of 1 since the primary data the indicator is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Evaluates to make sure we have at least 20 (default value of BarsRequiredToPlot)
     // or more bars in both Bars objects before continuing.
     if (CurrentBars[0] < BarsRequiredToPlot || CurrentBars[1] < BarsRequiredToPlot)
         return;

     // Indicator script logic calculation code...

}

```

### Strategy ( **[BarsRequiredToTrade](https://developer.ninjatrader.com/docs/desktop/barsrequiredtotrade)**)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the script. It will automatically be assigned
         // a Bars object index of 1 since the primary data the indicator is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Evaluates to make sure we have at least 20 (default value of BarsRequiredToTrade)
     // or more bars in both Bars objects before continuing.
     if (CurrentBars[0] < BarsRequiredToTrade || CurrentBars[1] < BarsRequiredToTrade)
         return;

     // Strategy script logic calculation code...
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/currentbars\#definition)

Holds an array of int values representing the number of the current bar in a Bars object. An **int** value is added to this array when calling the **[AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries)** method. Its purpose is to provide access to the **[CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar)** of all Bars objects in a multi-instrument or multi-time frame script.

## Note

In **[multi series](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments)** processing, the CurrentBars starting value will be -1 until all series have processed the first bar.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/currentbars\#property-value)

An array of int values.

## Warning

Warning: This property should NOT be accessed within the **[OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange)** method before the State has reached State.DataLoaded.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/currentbars\#syntax)

`CurrentBars[int barSeriesIndex]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/currentbars\#examples)

### Indicator ( **[BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot)**)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the script. It will automatically be assigned
         // a Bars object index of 1 since the primary data the indicator is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Evaluates to make sure we have at least 20 (default value of BarsRequiredToPlot)
     // or more bars in both Bars objects before continuing.
     if (CurrentBars[0] < BarsRequiredToPlot || CurrentBars[1] < BarsRequiredToPlot)
         return;

     // Indicator script logic calculation code...

}

```

### Strategy ( **[BarsRequiredToTrade](https://developer.ninjatrader.com/docs/desktop/barsrequiredtotrade)**)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the script. It will automatically be assigned
         // a Bars object index of 1 since the primary data the indicator is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Evaluates to make sure we have at least 20 (default value of BarsRequiredToTrade)
     // or more bars in both Bars objects before continuing.
     if (CurrentBars[0] < BarsRequiredToTrade || CurrentBars[1] < BarsRequiredToTrade)
         return;

     // Strategy script logic calculation code...
}

```