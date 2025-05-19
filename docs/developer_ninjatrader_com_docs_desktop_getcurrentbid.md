## [Definition](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#definition)

Returns the current real-time bid price.

## Note

Notes:

1. When accessed during **State.Historical**, the [Close](https://developer.ninjatrader.com/docs/desktop/close) price of the evaluated bar is substituted. To access historical bid prices, please see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).
2. The **GetCurrentBid()** method runs on the bar series currently updating determined by the **BarsInProgress** property. For [multi-instrument](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) scripts, an additional int "barsSeriesIndex" parameter can be supplied which forces the method to run on an supplementary bar series.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#method-return-value)

A **double** value representing the current bid price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#syntax)

`GetCurrentBid()`

`GetCurrentBid(int barsSeriesIndex)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#parameters)

| Parameter | Description |
| --- | --- |
| **barsSeriesIndex** | An **int** value determining the bar series the method runs. Note: This optional parameter is reserved for multi-instrument scripts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Ensure we do not call GetCurrentBid() on historical data
   if (State == State.Historical)
     return;

   double currentBid = GetCurrentBid();
   Print("The Current Bid price is: " + currentBid);
   // The Current Bid price is: 1924.75
}

```

```jsx-150469391 csharp

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Example's Indicator";
   }
   if (State == State.Configure)
   {
     //Add MSFT as our additional data series
     AddDataSeries("MSFT", BarsPeriodType.Minute, 1);
   }
}

protected override void OnBarUpdate()
{
   // Ensure we do not call GetCurrentBid() on historical data
   if (State == State.Historical)
     return;

   if (BarsInProgress == 0)
   {
     double primaryBid = GetCurrentBid(0);
     Print("The Primary Bid price is: " + primaryBid);
     // The Primary Bid price is: 1924.75
   }

   if (BarsInProgress == 1)
   {
     double msftBid = GetCurrentBid(1);
     Print("MSFT's Current Bid price is: " + msftBid);
     // MSFT's Current Bid is: 43.63
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#definition)

Returns the current real-time bid price.

## Note

Notes:

1. When accessed during **State.Historical**, the [Close](https://developer.ninjatrader.com/docs/desktop/close) price of the evaluated bar is substituted. To access historical bid prices, please see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).
2. The **GetCurrentBid()** method runs on the bar series currently updating determined by the **BarsInProgress** property. For [multi-instrument](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) scripts, an additional int "barsSeriesIndex" parameter can be supplied which forces the method to run on an supplementary bar series.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#method-return-value)

A **double** value representing the current bid price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#syntax)

`GetCurrentBid()`

`GetCurrentBid(int barsSeriesIndex)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#parameters)

| Parameter | Description |
| --- | --- |
| **barsSeriesIndex** | An **int** value determining the bar series the method runs. Note: This optional parameter is reserved for multi-instrument scripts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcurrentbid\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Ensure we do not call GetCurrentBid() on historical data
   if (State == State.Historical)
     return;

   double currentBid = GetCurrentBid();
   Print("The Current Bid price is: " + currentBid);
   // The Current Bid price is: 1924.75
}

```

```jsx-150469391 csharp

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Example's Indicator";
   }
   if (State == State.Configure)
   {
     //Add MSFT as our additional data series
     AddDataSeries("MSFT", BarsPeriodType.Minute, 1);
   }
}

protected override void OnBarUpdate()
{
   // Ensure we do not call GetCurrentBid() on historical data
   if (State == State.Historical)
     return;

   if (BarsInProgress == 0)
   {
     double primaryBid = GetCurrentBid(0);
     Print("The Primary Bid price is: " + primaryBid);
     // The Primary Bid price is: 1924.75
   }

   if (BarsInProgress == 1)
   {
     double msftBid = GetCurrentBid(1);
     Print("MSFT's Current Bid price is: " + msftBid);
     // MSFT's Current Bid is: 43.63
   }
}

```