## [Definition](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#definition)

An event driven method which is called whenever a bar is updated. The frequency in which **OnBarUpdate** is called will be determined by the " [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate)" property. **OnBarUpdate()** is the method where all of your script's core bar based calculation logic should be contained.

## Note

Notes:

- For [multi-timeframe and instrument scripts](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments), the **OnBarUpdate** method is called for each Bars object of a strategy. You MUST filter for the exact bar update events using the " [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress)" property you want your system logic to execute against.
- Hosted indicators will need to be accessed by the hosting script to ensure **OnBarUpdate** functionality. This can be done by:
1. Calling [Update](https://developer.ninjatrader.com/docs/desktop/update) on the hosted indicator within the host script,
2. Including a plot in the hosted indicator and accessing the plot in the host script,
3. Including a plot in the hosted indicator and adding the indicator to the chart with [AddChartIndicator](https://developer.ninjatrader.com/docs/desktop/addchartindicator) (strategies only)

## [Related Methods and Properties](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#related-methods-and-properties)

| Method | Description |
| --- | --- |
| [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) | The primary Bars object time frame (period type and interval). |
| [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate) | Determines how often **OnBarUpdate()** is called for each bar. |
| [Count](https://developer.ninjatrader.com/docs/desktop/count) | The total number of bars or data points. |
| [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) | A number representing the current bar in a Bars object that the **OnBarUpdate()** method in an indicator or strategy is currently processing. |
| [IsDataSeriesRequired](https://developer.ninjatrader.com/docs/desktop/isdataseriesrequired) | Determines if a Data Series is required for calculating this NinjaScript object. |
| [IsFirstTickOfBar](https://developer.ninjatrader.com/docs/desktop/isfirsttickofbar) | Indicates if the incoming tick is the first tick of a new bar. |
| [IsResetOnNewTradingDays](https://developer.ninjatrader.com/docs/desktop/isresetonnewtradingdays) | Determines if the specified bar series is using Break at EOD. |
| [IsTickReplays](https://developer.ninjatrader.com/docs/desktop/istickreplays) | Indicates the specified bar series is using Tick Replay. |
| [Update()](https://developer.ninjatrader.com/docs/desktop/update) | Forces the **OnBarUpdate()** method to be called so that indicator values are updated to the current bar. |

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#syntax)

You must override this method with the following syntax:

**protected override void OnBarUpdate()**

## Note

Tip: The NinjaScript code wizards automatically generates the method syntax for you.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#parameters)

This method does not take any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CurrentBar < 1)
         return;

     // Compares the primary bar's low price to the 5-minute bar's low price
     if (Low[0] > Lows[1])
         Print("The current bar's low price is greater");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#definition)

An event driven method which is called whenever a bar is updated. The frequency in which **OnBarUpdate** is called will be determined by the " [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate)" property. **OnBarUpdate()** is the method where all of your script's core bar based calculation logic should be contained.

## Note

Notes:

- For [multi-timeframe and instrument scripts](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments), the **OnBarUpdate** method is called for each Bars object of a strategy. You MUST filter for the exact bar update events using the " [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress)" property you want your system logic to execute against.
- Hosted indicators will need to be accessed by the hosting script to ensure **OnBarUpdate** functionality. This can be done by:
1. Calling [Update](https://developer.ninjatrader.com/docs/desktop/update) on the hosted indicator within the host script,
2. Including a plot in the hosted indicator and accessing the plot in the host script,
3. Including a plot in the hosted indicator and adding the indicator to the chart with [AddChartIndicator](https://developer.ninjatrader.com/docs/desktop/addchartindicator) (strategies only)

## [Related Methods and Properties](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#related-methods-and-properties)

| Method | Description |
| --- | --- |
| [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) | The primary Bars object time frame (period type and interval). |
| [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate) | Determines how often **OnBarUpdate()** is called for each bar. |
| [Count](https://developer.ninjatrader.com/docs/desktop/count) | The total number of bars or data points. |
| [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) | A number representing the current bar in a Bars object that the **OnBarUpdate()** method in an indicator or strategy is currently processing. |
| [IsDataSeriesRequired](https://developer.ninjatrader.com/docs/desktop/isdataseriesrequired) | Determines if a Data Series is required for calculating this NinjaScript object. |
| [IsFirstTickOfBar](https://developer.ninjatrader.com/docs/desktop/isfirsttickofbar) | Indicates if the incoming tick is the first tick of a new bar. |
| [IsResetOnNewTradingDays](https://developer.ninjatrader.com/docs/desktop/isresetonnewtradingdays) | Determines if the specified bar series is using Break at EOD. |
| [IsTickReplays](https://developer.ninjatrader.com/docs/desktop/istickreplays) | Indicates the specified bar series is using Tick Replay. |
| [Update()](https://developer.ninjatrader.com/docs/desktop/update) | Forces the **OnBarUpdate()** method to be called so that indicator values are updated to the current bar. |

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#syntax)

You must override this method with the following syntax:

**protected override void OnBarUpdate()**

## Note

Tip: The NinjaScript code wizards automatically generates the method syntax for you.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#parameters)

This method does not take any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onbarupdate\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CurrentBar < 1)
         return;

     // Compares the primary bar's low price to the 5-minute bar's low price
     if (Low[0] > Lows[1])
         Print("The current bar's low price is greater");
}

```