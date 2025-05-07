## [Definition](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#definition)

Returns the current real-time ask volume.

## Note

1. When accessed during **State.Historical**, the [Volume](https://developer.ninjatrader.com/docs/desktop/volume) of the evaluated bar series is substituted. To access historical Ask Volumes, please see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).
2. The **GetCurrentAskVolume()** method runs on the bar series currently updating determined by the **BarsInProgress** property. For [multi-instrument](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) scripts, an additional int "barsSeriesIndex" parameter can be supplied which forces the method to run on a supplementary bar series.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#method-return-value)

A long value representing the current ask volume.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#syntax)

`GetCurrentAskVolume()`

`GetCurrentAskVolume(int barsSeriesIndex)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#parameters)

| Parameter | Description |
| --- | --- |
| barsSeriesIndex | An **int** value determining the bar series the method runs. Note: This optional parameter is reserved for multi-instrument scripts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   long currentAskVolume = GetCurrentAskVolume();
   Print("The Current Ask volume is: " + currentAskVolume);
   //The Current Ask volume is: 158
}

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
   }
   if (State == State.Configure)
   {
     //Add MSFT as our additional data series
     AddDataSeries("MSFT", BarsPeriodType.Minute, 1);
   }
}
protected override void OnBarUpdate()
{
   if(BarsInProgress == 0)
   {
     long currentAskVolume = GetCurrentAskVolume(0);
     Print("The Current Ask volume is: " + currentAskVolume);
     //The Current Ask volume is: 346
   }

   if(BarsInProgress == 1)

   {

     long msftAskVolume = GetCurrentAskVolume(1);

     Print("MSFT's Current Ask volume is: " + msftAskVolume);

     //MSFT's Current Ask volume is: 1548

   }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#definition)

Returns the current real-time ask volume.

## Note

1. When accessed during **State.Historical**, the [Volume](https://developer.ninjatrader.com/docs/desktop/volume) of the evaluated bar series is substituted. To access historical Ask Volumes, please see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).
2. The **GetCurrentAskVolume()** method runs on the bar series currently updating determined by the **BarsInProgress** property. For [multi-instrument](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) scripts, an additional int "barsSeriesIndex" parameter can be supplied which forces the method to run on a supplementary bar series.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#method-return-value)

A long value representing the current ask volume.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#syntax)

`GetCurrentAskVolume()`

`GetCurrentAskVolume(int barsSeriesIndex)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#parameters)

| Parameter | Description |
| --- | --- |
| barsSeriesIndex | An **int** value determining the bar series the method runs. Note: This optional parameter is reserved for multi-instrument scripts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getcurrentaskvolume\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   long currentAskVolume = GetCurrentAskVolume();
   Print("The Current Ask volume is: " + currentAskVolume);
   //The Current Ask volume is: 158
}

protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
   }
   if (State == State.Configure)
   {
     //Add MSFT as our additional data series
     AddDataSeries("MSFT", BarsPeriodType.Minute, 1);
   }
}
protected override void OnBarUpdate()
{
   if(BarsInProgress == 0)
   {
     long currentAskVolume = GetCurrentAskVolume(0);
     Print("The Current Ask volume is: " + currentAskVolume);
     //The Current Ask volume is: 346
   }

   if(BarsInProgress == 1)

   {

     long msftAskVolume = GetCurrentAskVolume(1);

     Print("MSFT's Current Ask volume is: " + msftAskVolume);

     //MSFT's Current Ask volume is: 1548

   }

```