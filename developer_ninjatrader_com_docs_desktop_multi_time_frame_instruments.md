## [Multi-Series Scripting Overview](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#multi-series-scripting-overview)

NinjaScript supports multiple time frames and instruments in a single script. This is possible because you can add additional Bars objects to indicators or strategies, in addition to the primary Bars object to which they are applied. A Bars object represents all of the bars of data on a chart. For example, if you had a **MSFT** 1 minute chart with 200 bars on it, the 200 bars represent one Bars object. In addition to adding Bars objects for reference or for use with indicator methods, you can execute trades across all the different instruments in a script. There is extreme flexibility in the NinjaScript model that NinjaTrader uses for multiple-bars scripts, so it is very important that you understand how it all works before you incorporate additional Bars objects in a script. An important fact to understand is that NinjaScript is truly event driven; every Bars object in a script will call the **OnBarUpdate()** method. The significance of this will become evident throughout this page.

## Note

If using **OnMarketData()**, a subscription will be created on all bars series added in your indicator or strategy (even if the instrument is the same). The market data subscription behavior occurs both in real-time and during **TickReplay** historical.

It is also important that you understand the following method and properties:

- [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries)
- [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray)
- [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress)
- [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars)

## Note

As we move through this section, the term "Primary Bars" will be used and for the purpose of clarification, this will always refer to the first Bars object loaded into a script. For example, if you apply a script on **MSFT** 1 minute chart, the primary Bars would be **MSFT** 1 minute data set.

This section is written in sequential fashion. Example code is re-used and built upon from sub section to sub section.

## [Data processing sequence](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#data-processing-sequence)

Understanding the sequence in which bars series process and the granularity provided by market data vendors is essential for efficient multi-series development. Let’s assume we have two series (primary and secondary) in our script, which is representing the same instrument, yet different intervals. During historical data processing, NinjaTrader updates the two series strictly according to their timestamps, calling the primary bar series of the corresponding timestamps first, and then calling the secondary series.

## Note

Historical bars are processed according to their timestamps with the primary bars first, followed by the secondary, which is NOT guaranteed to be the same sequence that these events occurred in real-time. If your development requires ticks to process in the same sequence historically as well as in real-time, you will need to enable **Tick Replay** (utilizes more PC resources).

## [Shared Timestamps](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#shared-timestamps)

In circumstances where multiple bars share the same exact timestamps, your primary bars series will always be processed first, followed by the secondary bars series (regardless of the period value used). Consequently, if you were looking to obtain a value from the secondary bars series, it would ONLY be available after the primary series has been processed for the same timestamps. For example, consider a news event or a fast moving market with an influx of ticks (session begin/session end). This activity will yield a wider range of bars than usual and the probability of those bars sharing the same timestamps increases. If such a succession of bars with the same timestamps is processed, the primary bars would be processed first and then the secondary bars during this period.

## Note

Tip: While the following behavior applies to all period types, the effects are amplified on smaller time frames. If you plan on using a high-resolution (e.g., 1-second, 10-tick, etc), please make sure to thoroughly read and understand the material below when working with these additional series. It is also important to keep in mind that the granularity of the timestamps will dictate how accurately NinjaTrader can synchronize the bars in historical processing. The available level of granularity will be dependent upon which [data provider](https://ninjatrader.com/support/helpGuides/nt8/data_by_provider.htm) you use with NinjaTrader.

Let’s look at an illustration of how the multi-time frame bar processing sequence can be understood. Assume our primary series is a 5-tick bar series, and our secondary series is a 1-tick bar series. The time of day is near the session close, so a rapid sequence of bars is generated.

In the figure below, the 1st group of bars (colored orange), and the 4th group of bars (colored purple) process in an exact logical sequence (i.e., a single primary bar update, followed by five secondary series updates). This is because each bar in these groups have unique timestamps and NinjaTrader can synchronize those bars logically in the exact time sequence each series updated. However, all of the bars marked with red text share the same exact timestamps down to the millisecond (14:59:00:480). Since there were six ticks in sequence with the shared timestamps, this range of ticks expands two of the primary bars (colored green and blue). As a result, the primary bar #3 appears to update earlier when compared to the secondary series. In reality, both bars series are incrementing in their exact sequence according to the timestamps of each series.

## [Adding Additional Bars Objects to NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#adding-additional-bars-objects-to-ninjascript)

Additional Bars are added to a script via the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method in the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method when the [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Configure. When a Bars object is added to a script, it is also added to the [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) array. BarsArray functions like a container in the script that holds all Bars objects added to the script. As a Bars object is added to the script, it's added to BarsArray and given an index number so we can retrieve this Bars object later.

## Warning

- This method should ONLY be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.Configure.
- Arguments supplied to **AddDataSeries()** should be hardcoded and NOT dependent on run-time variables which cannot be reliably obtained during [State.Configure](https://developer.ninjatrader.com/docs/desktop/state) (e.g., [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument), [Bars](https://developer.ninjatrader.com/docs/desktop/bars), or user input). Attempting to add a data series dynamically is NOT guaranteed and therefore should be avoided. Trying to load bars dynamically may result in an error similar to: Unable to load bars series. Your NinjaScript may be trying to use an additional data series dynamically in an unsupported manner.
- When instantiating indicators in a Multi-Series script in [OnStateChange](https://developer.ninjatrader.com/docs/desktop/onstatechange), the input any hosted indicator is running on should be explicitly stated (since a specific [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) is not guaranteed).

For the purpose of demonstration, let's assume that a **MSFT** 1 minute bar is our primary Bars object (set when the script is applied to a 1 minute **MSFT** chart) and that the **OnStateChange()** method is adding a 3 minute Bars object of **MSFT**, then adding a 1 minute Bars object of **AAPL**, for a total of 3 unique Bars objects.

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name   = "Multi-Time Frame & Instruments Example";
    }
    else if (State == State.Configure)
    {
        AddDataSeries(BarsPeriodType.Minute, 3);
        AddDataSeries("AAPL", BarsPeriodType.Minute, 1);
    }
}

```

## Note

To maximize data loading performance, any NinjaScript object (indicator or strategy as host) which references a multi-series indicator which calls **AddDataSeries** must include its own calls to **AddDataSeries()**. For example, if the code above was included in an indicator, and that indicator was referenced in a NinjaScript strategy, then the hosting strategy will need to include the same calls to **AddDataSeries()**. When the strategy adds the additional Bars objects, the calls to **AddDataSeries()** within the indicator will be ignored. If the Bars objects are not added by the strategy in such cases, and error will be thrown in the Log tab of the Control Center that would read - "A hosted indicator tried to load additional data. All data must first be loaded by the hosting NinjaScript in its configure state."

## Note

[Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) is the base class for [PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries), [TimeSeries](https://developer.ninjatrader.com/docs/desktop/timeseries), and [VolumeSeries](https://developer.ninjatrader.com/docs/desktop/volumeseries). Rather than using one of these pre-defined derived classes, you can create your own Series< `t` \> collection to hold any Type that you choose. The advantage that Series< `t` \> has over other collections is that it can be quickly initialized to contain a number of index slots equal to the number of bars in one of the Bars objects on the chart, with each index slot corresponding to a specific bar.

### Initializing a Series< `t` \> with BarsArray

A Series< `t` \> can be constructed by passing in a specific index of BarsArray. Initializing a Series< `t` \> this way produces an empty Series< `t` \> container holding the same number of index slots as the BarsArray that was passed in as an argument. For example, assuming that BarsArray\[1\] holds 500 bars, the code below will create an empty Series< `t` \> with 500 index slots:

```jsx-150469391 csharp
private Series<`double`> myEmptyIndexedSeries; // Define a Series<`t`> object variable.

// Initialize the Series object to have the same number of index slots as BarsArray[1]
protected override void OnStateChange()
{
    if (State == State.DataLoaded)
    {
        // Passing in BarsArray[1] as an argument results in an empty Series with an identical number of index slots
        myEmptyIndexedSeries = new Series<double>(BarsArray[1]);
    }
}

```

This method of initializing a Series< `t` \> can be especially useful when you wish to store user-defined information related to each bar in a Bars object on the chart. This process ensures that index slots are available for every bar on the chart right away.

### Initializing a Series< `t` \> with an Indicator Method

Passing in an indicator method as an argument when instantiating a Series< `t` \> object provides an alternative to the process outlined above. Because indicator methods already contain Series objects synced to the bars on a chart, they can be used to inform the constructor of Series< `t` \> of how many index slots to create.

```jsx-150469391 csharp
// Declare two Series objects
private Series<double> primarySeries;
private Series<double> secondarySeries;

protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Adds a secondary bar object to the strategy.
        AddDataSeries(BarsPeriodType.Minute, 5);
    }
    else if (State == State.DataLoaded)
    {
        // Syncs a Series object to the primary bar object
        primarySeries = new Series<double>(this);

        /* Syncs another Series object to the secondary bar object.
         We use an arbitrary indicator overloaded with an ISeries`<double>` input to achieve the sync.
         The indicator can be any indicator. The Series<double> will be synced to whatever the
         BarsArray[] is provided.*/
        secondarySeries = new Series<double>(SMA(BarsArray[1], 50));

        // Stop-loss orders are placed 5 ticks below average entry price
        SetStopLoss(CalculationMode.Ticks, 5);

        // Profit target orders are placed 10 ticks above average entry price
        SetProfitTarget(CalculationMode.Ticks, 10);
    }
}

```

## [How Bars Data is Referenced](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#how-bars-data-is-referenced)

Understanding how multi-time frame bars are processed and which OHLCV data is referenced is critical.

Figure 1 below demonstrates the concept of bar processing on historical data or in real-time when the [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate) property is set to Calculate.OnBarClose. The 1 minute bars in yellow will only know the OHLCV of the 3 minute bar in yellow. The 1 minute bars in cyan will only know the OHLCV data of the 3 minute bar in cyan. Take a look at "Bar #5," which is the fifth one minute bar. If you wanted to know the current high value for the 3-minute time frame, you would get the value of the first 3 minute bar since this is the last "closed" bar. The second 3 minute bar (cyan) would not be known at that time.

Contrast the above image and concept with the image below, which demonstrates bar processing in real-time when the Calculate property is set to Calculate.OnEachTick (tick by tick processing) or Calculate.OnPriceChange (processing by change in price). The 1 minute bars in yellow will know the current OHLCV of the 3 minute bar in yellow (second 3 minute bar) which is still in formation and has not yet closed.

If you have a multi-time frame script in real-time, and it is processing tick by tick instead of on the close of each bar, understand that the OHLCV data you access in real-time is different than on historical data.

Below is another example to illustrate this point:

Your script has complex logic that changes the bar color on the chart. You are running tick by tick, as per the above "Figure 2" image, the 5th 1 minute bar is looking at OHLCV data from the second 3 minute bar. Your script changes the fifth 1 minute bar color to green. In the future, you reload your script into the chart and the fifth 1 minute bar is now a historical bar. As per Figure 1 above, the fifth 1 minute bar now references the OHLCV data of the first 3 minute bar (instead of the 2nd 3 minute bar as per Figure 2) and as a result, your script logic condition for coloring the bar green is no longer valid. The result is that now your chart looks different.

### Special considerations for session boundaries

Bars are not considered closed until the first tick of the following bar comes in (see also "True Event Driven OnBarUpdate" below). As a consequence, if the above series 2 cyan bar represents the final bar of a session, and this bar is referenced from the matching series 1 cyan bar, or anywhere after that, the data from the close of the bar (the beginning of the next session) will be referenced. If you plan on using multiple session templates, you will need to handle the final bar of a trading day case explicitly (for example, using a [Session Iterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) and the [PriorDayOHLC](https://developer.ninjatrader.com/docs/desktop/prior_day_ohlc) if you would like to reference data from the end of the previous trading day instead of the beginning of the current trading day.

## [Using Bars Objects as Input to Indicator Methods](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#using-bars-objects-as-input-to-indicator-methods)

In the sub-section above, the concept of index values was introduced. This is a critical concept to understand since it is used consistently when working with multi-Bars script.

Let's demonstrate this concept:

Carrying on from the example above, our primary Bars is set from a **MSFT** 1 minute chart.

- **MSFT** 1 minute Bars is given an index value of 0 in BarsArray.
- In the **OnStateChange()** method we added a **MSFT** 3 minute Bars object and an **AAPL** 1 minute Bars object to the script.
- **MSFT** 3 minute Bars is given an index value of 1 in BarsArray.
- **AAPL** 1 minute Bars is given an index value of 2 in BarsArray.

Incremental index values are given to Bars objects as they are added to a script. If there are 10 Bars objects in a script, then you will have index values ranging from 0 to 9.

Our script now has 3 Bars objects in the container BarsArray. From this point forward, we can ask this container to give us the Bars object we want to work with by providing the index value. The syntax for this is:

```jsx-1168641291 csharp
BarsArray[index]

```

This allows us to get the correct Bars object and use it as input for an [indicator method](https://developer.ninjatrader.com/docs/desktop/indicators). For example:

```jsx-1168641291 csharp
ADX(14)[0] > 30 && ADX(BarsArray[2], 14)[0] > 30

```

The above expression in English would translate to:

If the 14 period ADX of **MSFT** 1 minute is greater than 30 and the 14 period ADX of **AAPL** 1 minute is greater than 30.

Before we can apply this concept, we need to ensure that our Bars objects actually contain bars that we can use to run calculations. This can be done by checking the [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars) array, which returns the number of the current bar in each Bars object. Using this in conjunction with [BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot) will ensure each Bars object has sufficient data before we begin processing.

## Note

By default, the CurrentBars starting value will be -1 until all series have processed the first bar.

```jsx-150469391 csharp
OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning.
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;
}

```

Putting it all together now, the following example checks if the current CCI value for all Bars objects is above 200. You will notice that BarsInProgress is used. This is to check which Bars object is calling the **OnBarUpdate()** method. More on this later in this section.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    if (BarsInProgress == 0)
    {
        if (CCI(20)[0] > 200 && CCI(BarsArray[1], 20)[0] > 200 && CCI(BarsArray[2], 20)[0] > 200)
        {
            // Do something
        }
    }
}

```

## [True Event Driven OnBarUpdate() Method](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#true-event-driven-onbarupdate()-method)

Since a NinjaScript script is truly event driven, the **OnBarUpdate()** method is called for every bar update event for each Bars object added to the script. This model maximizes flexibility. For example, you could have multiple trading systems combined into one strategy, each dependent on one another. For example, you could have a 1 minute **MSFT** Bars object and a 1 minute **AAPL** Bars object, process different trading rules on each Bars object and check to see if **MSFT** is long when **AAPL** trading logic is being processed.

The [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property is used to identify which Bars object is calling the **OnBarUpdate()** method. This allows you to filter out the events that you are looking for.

Continuing our example above, let's take a closer look at what is happening. Remember, we have three Bars objects working in our script, a primary Bars **MSFT** 1 minute, an **MSFT** 3 minute, and an **AAPL** 1 minute.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        if (Close[0] > Open[0])
            // Do something
    }

    // Checks if OnBarUpdate() is called from an update on **MSFT** 3 minute Bars
    if (BarsInProgress == 1)
    {
        if (Close[0] > Open[0])
            // Do something
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars
    if (BarsInProgress == 2)
    {
        if (Close[0] > Open[0])
            // Do something
    }
}

```

What is important to understand in the above sample code is that we have "if" branches that check to see what Bars object is calling the **OnBarUpdate()** method in order to process relevant trading logic. If we only wanted to process the events from the primary Bars we could add the following condition at the top of the **OnBarUpdate()** method:

```jsx-150469391 csharp
if (BarsInProgress != 0)
    return;

```

What is also important to understand is the concept of context. When the **OnBarUpdate()** method is called, it will be called within the context of the calling Bars object. This means that if the primary Bars triggers the **OnBarUpdate()** method, all indicator methods and price data will point to that Bars object's data. Notice how the statement "if (Close\[0\] > Open\[0\]" exists under each "if" branch in the code sample above. The values returned by Close\[0\] and Open\[0\] will be the close and open price values for the calling Bars object. So when the **BarsInProgress == 0** (primary Bars) the close value returned is the close price of the **MSFT** 1 minute bar. When the **BarsInProgress == 1** the close value returned is the close price of the **MSFT** 3 minute Bars object.

## Note

Notes:

- A multi-series script only processes bar update events from the primary Bars (the series the script is applied to) and any additional Bars objects the script adds itself. Additional Bars objects from a multi-series chart or from other multi-series scripts that may be running concurrently will not be processed by this multi-series script.
- If a multi-series script adds an additional Bars object that already exists on the chart, the script will use the preexisting series instead of creating a new one to conserve memory. This includes that series' [session template](https://ninjatrader.com/support/helpGuides/nt8/?using_the_trading_hours_window.htm) as applied from the chart. If the Bars object does not exist on the chart, the session template of the added Bars object will be the session template of the primary Bars object. If the primary Bars object is using the " `<use instrument="" settings="">`" session template, then the additional Bars objects will use the default session templates as defined for their particular instruments in the [Instruments](https://developer.ninjatrader.com/docs/desktop/instruments) window.

- In a multi-series script, CurrentBars starting value will be -1 until all series have processed the first bar. To ensure you have satisfied this requirement on all your Bars objects, it is recommend you start your **OnBarUpdate()** method with [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars) checks, as seen in the code sample above.

- A multi-series indicator will hold the same number of data points for plots as the primary series. Setting values to plots should be done in the primary series in **OnBarUpdate()**. If you are using calculations based off of a larger secondary series, it may plot like a step ladder because there are more data points available than there are actual meaningful data values.
- The default [CloseStrategy()](https://developer.ninjatrader.com/docs/desktop/closestrategy) handling will only be applied to the primary series of a MultiSeries NinjaScript strategy.
- An indicator / strategy with multiple DataSeries of the same instrument will only process realtime **OnBarUpdate()** calls when a tick occurs in session of the trading hour templates of all added series. Any ticks not processed will be queued and processed as a tick comes in for all subsequent DataSeries.

## [Accessing the Price Data in a Multi-Bars NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#accessing-the-price-data-in-a-multi-bars-ninjascript)

As you probably know already, you can access the current bar's closing price with the following statement:

```jsx-1168641291 csharp
Close[0];

```

You can also access price data such as the close price of other Bars objects at any time. This is accomplished by accessing the [Opens](https://developer.ninjatrader.com/docs/desktop/opens), [Highs](https://developer.ninjatrader.com/docs/desktop/highs), [Lows](https://developer.ninjatrader.com/docs/desktop/lows), [Closes](https://developer.ninjatrader.com/docs/desktop/closes), [Volumes](https://developer.ninjatrader.com/docs/desktop/volumeseries), [Medians](https://developer.ninjatrader.com/docs/desktop/medians), [Typicals](https://developer.ninjatrader.com/docs/desktop/typicals) and [Times](https://developer.ninjatrader.com/docs/desktop/timeseries) series by index value. These properties hold collections (containers) that hold their named values for all Bars objects in a script.

Continuing with our example code above, if you wanted to access the high price of the **MSFT** 3 minute Bars object at index 1 you would write:

```jsx-1168641291 csharp
Highs[1][0];

```

This is just saying "give me the series of high prices for the Bars object at index 1 'Highs\[1\]' and return to me the current high value '\[0\]'. If the BarsInProgress index was equal to 1, the current context is of the **MSFT** 3 min Bars object so you could just write:

```jsx-1168641291 csharp
High[0];

```

The following example demonstrates various ways to access price data.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        double primaryClose = Close[0];
        double msft3minClose = Closes[1][0];
        double aapl1minClose = Closes[2][0];

        // primaryClose could also be expressed as
        // primaryClose = Closes[0][0];
    }

    // Checks if OnBarUpdate() is called from an update on **MSFT** 3 minute Bars object
    if (BarsInProgress == 1)
    {
        double primaryClose = Closes[0][0];
        double msft3minClose = Close[0];
        double aapl1minClose = Closes[2][0];
    }
}

```

## [Entering, Exiting and Retrieving Position Information](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#entering,-exiting-and-retrieving-position-information)

This section is relevant for NinjaScript strategies only. Entry and Exit methods are executed within the BarsInProgress context. Let's demonstrate with an example:

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is an indicator, use BarsRequiredToPlot instead of BarsRequiredToTrade
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        // Submits a buy market order for **MSFT**
        EnterLong();
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars object
    if (BarsInProgress == 2)
    {
        // Submits a buy market order for **AAPL**
        EnterLong();

        // Submits a buy market for **MSFT** when OnBarUpdate() is called for **AAPL**
        EnterLong(0, 100, "BUY MSFT");
    }
}

```

As you can see above, orders are submitted for **MSFT** when BarsInProgress is equal to 0 and for **AAPL** when BarsInProgress is equal to 2. The orders submitted are within the context of the Bars object calling the **OnBarUpdate()** method and the instrument associated to the calling Bars object. There is one exception, which is the order placed for **MSFT** within the context of the **OnBarUpdate()** call for **AAPL**. Each order method has a variation that allows you to specify the BarsInProgress index value which enables submission of orders for any instrument within the context of another instrument.

## Note

Notes:

1. Should you have multiple Bars objects of the same instrument while using Set() methods in your strategy, you should only submit orders for this instrument to the first Bars context of that instrument. This is to ensure your order logic is processed correctly and any necessary order amendments are done properly.
2. Should you have multiple Bars objects of the same instrument while using options to terminate orders/positions at the end of the session (TIF=Day or [IsExitOnSessionCloseStrategy](https://developer.ninjatrader.com/docs/desktop/isexitonsessionclosestrategy) =true), you should not submit orders to Bars objects other than the first Bars context for that instrument when on the last bar of the session. This is necessary because some of the end of session handling is applied only to the first Bars context of an instrument, and submitting orders to other Bars objects for that instrument can bypass the end-of-session handling.
3. For [advanced order methods](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling), if you DO NOT specify a BarsInProgress , the order will be submitted to the current bars in progress updating.  If the current BarsInProgress is a higher time frame, this could delay the time that the order is filled during historical backtesting.  As a result, you should always submit historical orders to the most granular of time frames.
4. When backtesting and submitting orders 'On bar close' and utilizing **OnExecutionUpdate** or **OnOrderUpdate** to submit orders, these orders will be processed immediately and filled by the fill engine depending on if the order satisfies its fill condition. This evaluation is done by looking ahead to the next bar of the current series. This is done prior to any secondary higher granularity series having a chance to run its 'OnBarUpdate' logic. If you planned on running order logic in your highest granularity added series then please insure that you submit orders in all cases to the highest granularity series.

The [Position](https://developer.ninjatrader.com/docs/desktop/position) property always references the position of the instrument of the current context. If the BarsInProgress is equal to 2 ( **AAPL** 1 minute Bars), Position would refer to the position being held for **AAPL**. The [Positions](https://developer.ninjatrader.com/docs/desktop/positions) property holds a collection of Position objects for each instrument in a strategy. Note that there is a critical difference here. Throughout this entire section we have been dealing with Bars objects. Although in our sample we have three Bars objects ( **MSFT** 1 and 3 min and **AAPL** 1 min) we only have two instruments in the strategy.

- **MSFT** position is given an index value of 0.
- **AAPL** position is given an index value of 1.

In the example below, when the **OnBarUpdate()** method is called for the primary Bars we also check if the position held for **AAPL** is NOT flat and then enter a long position in **MSFT**. The net result of this strategy is that a long position is entered for **AAPL**, and then once **AAPL** is long, we go long **MSFT**.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is an indicator, use BarsRequiredToPlot instead of BarsRequiredToTrade
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0 && Positions[1].MarketPosition != MarketPosition.Flat)
    {
        // Submits a buy market order for **MSFT**
        EnterLong();
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars
    if (BarsInProgress == 2)
    {
        // Submits a buy market order for **AAPL**
        EnterLong();
    }
}

```

## [Multi-Series Scripting Overview](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#multi-series-scripting-overview)

NinjaScript supports multiple time frames and instruments in a single script. This is possible because you can add additional Bars objects to indicators or strategies, in addition to the primary Bars object to which they are applied. A Bars object represents all of the bars of data on a chart. For example, if you had a **MSFT** 1 minute chart with 200 bars on it, the 200 bars represent one Bars object. In addition to adding Bars objects for reference or for use with indicator methods, you can execute trades across all the different instruments in a script. There is extreme flexibility in the NinjaScript model that NinjaTrader uses for multiple-bars scripts, so it is very important that you understand how it all works before you incorporate additional Bars objects in a script. An important fact to understand is that NinjaScript is truly event driven; every Bars object in a script will call the **OnBarUpdate()** method. The significance of this will become evident throughout this page.

## Note

If using **OnMarketData()**, a subscription will be created on all bars series added in your indicator or strategy (even if the instrument is the same). The market data subscription behavior occurs both in real-time and during **TickReplay** historical.

It is also important that you understand the following method and properties:

- [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries)
- [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray)
- [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress)
- [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars)

## Note

As we move through this section, the term "Primary Bars" will be used and for the purpose of clarification, this will always refer to the first Bars object loaded into a script. For example, if you apply a script on **MSFT** 1 minute chart, the primary Bars would be **MSFT** 1 minute data set.

This section is written in sequential fashion. Example code is re-used and built upon from sub section to sub section.

## [Data processing sequence](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#data-processing-sequence)

Understanding the sequence in which bars series process and the granularity provided by market data vendors is essential for efficient multi-series development. Let’s assume we have two series (primary and secondary) in our script, which is representing the same instrument, yet different intervals. During historical data processing, NinjaTrader updates the two series strictly according to their timestamps, calling the primary bar series of the corresponding timestamps first, and then calling the secondary series.

## Note

Historical bars are processed according to their timestamps with the primary bars first, followed by the secondary, which is NOT guaranteed to be the same sequence that these events occurred in real-time. If your development requires ticks to process in the same sequence historically as well as in real-time, you will need to enable **Tick Replay** (utilizes more PC resources).

## [Shared Timestamps](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#shared-timestamps)

In circumstances where multiple bars share the same exact timestamps, your primary bars series will always be processed first, followed by the secondary bars series (regardless of the period value used). Consequently, if you were looking to obtain a value from the secondary bars series, it would ONLY be available after the primary series has been processed for the same timestamps. For example, consider a news event or a fast moving market with an influx of ticks (session begin/session end). This activity will yield a wider range of bars than usual and the probability of those bars sharing the same timestamps increases. If such a succession of bars with the same timestamps is processed, the primary bars would be processed first and then the secondary bars during this period.

## Note

Tip: While the following behavior applies to all period types, the effects are amplified on smaller time frames. If you plan on using a high-resolution (e.g., 1-second, 10-tick, etc), please make sure to thoroughly read and understand the material below when working with these additional series. It is also important to keep in mind that the granularity of the timestamps will dictate how accurately NinjaTrader can synchronize the bars in historical processing. The available level of granularity will be dependent upon which [data provider](https://ninjatrader.com/support/helpGuides/nt8/data_by_provider.htm) you use with NinjaTrader.

Let’s look at an illustration of how the multi-time frame bar processing sequence can be understood. Assume our primary series is a 5-tick bar series, and our secondary series is a 1-tick bar series. The time of day is near the session close, so a rapid sequence of bars is generated.

In the figure below, the 1st group of bars (colored orange), and the 4th group of bars (colored purple) process in an exact logical sequence (i.e., a single primary bar update, followed by five secondary series updates). This is because each bar in these groups have unique timestamps and NinjaTrader can synchronize those bars logically in the exact time sequence each series updated. However, all of the bars marked with red text share the same exact timestamps down to the millisecond (14:59:00:480). Since there were six ticks in sequence with the shared timestamps, this range of ticks expands two of the primary bars (colored green and blue). As a result, the primary bar #3 appears to update earlier when compared to the secondary series. In reality, both bars series are incrementing in their exact sequence according to the timestamps of each series.

## [Adding Additional Bars Objects to NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#adding-additional-bars-objects-to-ninjascript)

Additional Bars are added to a script via the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method in the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method when the [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Configure. When a Bars object is added to a script, it is also added to the [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) array. BarsArray functions like a container in the script that holds all Bars objects added to the script. As a Bars object is added to the script, it's added to BarsArray and given an index number so we can retrieve this Bars object later.

## Warning

- This method should ONLY be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.Configure.
- Arguments supplied to **AddDataSeries()** should be hardcoded and NOT dependent on run-time variables which cannot be reliably obtained during [State.Configure](https://developer.ninjatrader.com/docs/desktop/state) (e.g., [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument), [Bars](https://developer.ninjatrader.com/docs/desktop/bars), or user input). Attempting to add a data series dynamically is NOT guaranteed and therefore should be avoided. Trying to load bars dynamically may result in an error similar to: Unable to load bars series. Your NinjaScript may be trying to use an additional data series dynamically in an unsupported manner.
- When instantiating indicators in a Multi-Series script in [OnStateChange](https://developer.ninjatrader.com/docs/desktop/onstatechange), the input any hosted indicator is running on should be explicitly stated (since a specific [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) is not guaranteed).

For the purpose of demonstration, let's assume that a **MSFT** 1 minute bar is our primary Bars object (set when the script is applied to a 1 minute **MSFT** chart) and that the **OnStateChange()** method is adding a 3 minute Bars object of **MSFT**, then adding a 1 minute Bars object of **AAPL**, for a total of 3 unique Bars objects.

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name   = "Multi-Time Frame & Instruments Example";
    }
    else if (State == State.Configure)
    {
        AddDataSeries(BarsPeriodType.Minute, 3);
        AddDataSeries("AAPL", BarsPeriodType.Minute, 1);
    }
}

```

## Note

To maximize data loading performance, any NinjaScript object (indicator or strategy as host) which references a multi-series indicator which calls **AddDataSeries** must include its own calls to **AddDataSeries()**. For example, if the code above was included in an indicator, and that indicator was referenced in a NinjaScript strategy, then the hosting strategy will need to include the same calls to **AddDataSeries()**. When the strategy adds the additional Bars objects, the calls to **AddDataSeries()** within the indicator will be ignored. If the Bars objects are not added by the strategy in such cases, and error will be thrown in the Log tab of the Control Center that would read - "A hosted indicator tried to load additional data. All data must first be loaded by the hosting NinjaScript in its configure state."

## Note

[Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) is the base class for [PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries), [TimeSeries](https://developer.ninjatrader.com/docs/desktop/timeseries), and [VolumeSeries](https://developer.ninjatrader.com/docs/desktop/volumeseries). Rather than using one of these pre-defined derived classes, you can create your own Series< `t` \> collection to hold any Type that you choose. The advantage that Series< `t` \> has over other collections is that it can be quickly initialized to contain a number of index slots equal to the number of bars in one of the Bars objects on the chart, with each index slot corresponding to a specific bar.

### Initializing a Series< `t` \> with BarsArray

A Series< `t` \> can be constructed by passing in a specific index of BarsArray. Initializing a Series< `t` \> this way produces an empty Series< `t` \> container holding the same number of index slots as the BarsArray that was passed in as an argument. For example, assuming that BarsArray\[1\] holds 500 bars, the code below will create an empty Series< `t` \> with 500 index slots:

```jsx-150469391 csharp
private Series<`double`> myEmptyIndexedSeries; // Define a Series<`t`> object variable.

// Initialize the Series object to have the same number of index slots as BarsArray[1]
protected override void OnStateChange()
{
    if (State == State.DataLoaded)
    {
        // Passing in BarsArray[1] as an argument results in an empty Series with an identical number of index slots
        myEmptyIndexedSeries = new Series<double>(BarsArray[1]);
    }
}

```

This method of initializing a Series< `t` \> can be especially useful when you wish to store user-defined information related to each bar in a Bars object on the chart. This process ensures that index slots are available for every bar on the chart right away.

### Initializing a Series< `t` \> with an Indicator Method

Passing in an indicator method as an argument when instantiating a Series< `t` \> object provides an alternative to the process outlined above. Because indicator methods already contain Series objects synced to the bars on a chart, they can be used to inform the constructor of Series< `t` \> of how many index slots to create.

```jsx-150469391 csharp
// Declare two Series objects
private Series<double> primarySeries;
private Series<double> secondarySeries;

protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Adds a secondary bar object to the strategy.
        AddDataSeries(BarsPeriodType.Minute, 5);
    }
    else if (State == State.DataLoaded)
    {
        // Syncs a Series object to the primary bar object
        primarySeries = new Series<double>(this);

        /* Syncs another Series object to the secondary bar object.
         We use an arbitrary indicator overloaded with an ISeries`<double>` input to achieve the sync.
         The indicator can be any indicator. The Series<double> will be synced to whatever the
         BarsArray[] is provided.*/
        secondarySeries = new Series<double>(SMA(BarsArray[1], 50));

        // Stop-loss orders are placed 5 ticks below average entry price
        SetStopLoss(CalculationMode.Ticks, 5);

        // Profit target orders are placed 10 ticks above average entry price
        SetProfitTarget(CalculationMode.Ticks, 10);
    }
}

```

## [How Bars Data is Referenced](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#how-bars-data-is-referenced)

Understanding how multi-time frame bars are processed and which OHLCV data is referenced is critical.

Figure 1 below demonstrates the concept of bar processing on historical data or in real-time when the [Calculate](https://developer.ninjatrader.com/docs/desktop/calculate) property is set to Calculate.OnBarClose. The 1 minute bars in yellow will only know the OHLCV of the 3 minute bar in yellow. The 1 minute bars in cyan will only know the OHLCV data of the 3 minute bar in cyan. Take a look at "Bar #5," which is the fifth one minute bar. If you wanted to know the current high value for the 3-minute time frame, you would get the value of the first 3 minute bar since this is the last "closed" bar. The second 3 minute bar (cyan) would not be known at that time.

Contrast the above image and concept with the image below, which demonstrates bar processing in real-time when the Calculate property is set to Calculate.OnEachTick (tick by tick processing) or Calculate.OnPriceChange (processing by change in price). The 1 minute bars in yellow will know the current OHLCV of the 3 minute bar in yellow (second 3 minute bar) which is still in formation and has not yet closed.

If you have a multi-time frame script in real-time, and it is processing tick by tick instead of on the close of each bar, understand that the OHLCV data you access in real-time is different than on historical data.

Below is another example to illustrate this point:

Your script has complex logic that changes the bar color on the chart. You are running tick by tick, as per the above "Figure 2" image, the 5th 1 minute bar is looking at OHLCV data from the second 3 minute bar. Your script changes the fifth 1 minute bar color to green. In the future, you reload your script into the chart and the fifth 1 minute bar is now a historical bar. As per Figure 1 above, the fifth 1 minute bar now references the OHLCV data of the first 3 minute bar (instead of the 2nd 3 minute bar as per Figure 2) and as a result, your script logic condition for coloring the bar green is no longer valid. The result is that now your chart looks different.

### Special considerations for session boundaries

Bars are not considered closed until the first tick of the following bar comes in (see also "True Event Driven OnBarUpdate" below). As a consequence, if the above series 2 cyan bar represents the final bar of a session, and this bar is referenced from the matching series 1 cyan bar, or anywhere after that, the data from the close of the bar (the beginning of the next session) will be referenced. If you plan on using multiple session templates, you will need to handle the final bar of a trading day case explicitly (for example, using a [Session Iterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) and the [PriorDayOHLC](https://developer.ninjatrader.com/docs/desktop/prior_day_ohlc) if you would like to reference data from the end of the previous trading day instead of the beginning of the current trading day.

## [Using Bars Objects as Input to Indicator Methods](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#using-bars-objects-as-input-to-indicator-methods)

In the sub-section above, the concept of index values was introduced. This is a critical concept to understand since it is used consistently when working with multi-Bars script.

Let's demonstrate this concept:

Carrying on from the example above, our primary Bars is set from a **MSFT** 1 minute chart.

- **MSFT** 1 minute Bars is given an index value of 0 in BarsArray.
- In the **OnStateChange()** method we added a **MSFT** 3 minute Bars object and an **AAPL** 1 minute Bars object to the script.
- **MSFT** 3 minute Bars is given an index value of 1 in BarsArray.
- **AAPL** 1 minute Bars is given an index value of 2 in BarsArray.

Incremental index values are given to Bars objects as they are added to a script. If there are 10 Bars objects in a script, then you will have index values ranging from 0 to 9.

Our script now has 3 Bars objects in the container BarsArray. From this point forward, we can ask this container to give us the Bars object we want to work with by providing the index value. The syntax for this is:

```jsx-1168641291 csharp
BarsArray[index]

```

This allows us to get the correct Bars object and use it as input for an [indicator method](https://developer.ninjatrader.com/docs/desktop/indicators). For example:

```jsx-1168641291 csharp
ADX(14)[0] > 30 && ADX(BarsArray[2], 14)[0] > 30

```

The above expression in English would translate to:

If the 14 period ADX of **MSFT** 1 minute is greater than 30 and the 14 period ADX of **AAPL** 1 minute is greater than 30.

Before we can apply this concept, we need to ensure that our Bars objects actually contain bars that we can use to run calculations. This can be done by checking the [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars) array, which returns the number of the current bar in each Bars object. Using this in conjunction with [BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot) will ensure each Bars object has sufficient data before we begin processing.

## Note

By default, the CurrentBars starting value will be -1 until all series have processed the first bar.

```jsx-150469391 csharp
OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning.
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;
}

```

Putting it all together now, the following example checks if the current CCI value for all Bars objects is above 200. You will notice that BarsInProgress is used. This is to check which Bars object is calling the **OnBarUpdate()** method. More on this later in this section.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    if (BarsInProgress == 0)
    {
        if (CCI(20)[0] > 200 && CCI(BarsArray[1], 20)[0] > 200 && CCI(BarsArray[2], 20)[0] > 200)
        {
            // Do something
        }
    }
}

```

## [True Event Driven OnBarUpdate() Method](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#true-event-driven-onbarupdate()-method)

Since a NinjaScript script is truly event driven, the **OnBarUpdate()** method is called for every bar update event for each Bars object added to the script. This model maximizes flexibility. For example, you could have multiple trading systems combined into one strategy, each dependent on one another. For example, you could have a 1 minute **MSFT** Bars object and a 1 minute **AAPL** Bars object, process different trading rules on each Bars object and check to see if **MSFT** is long when **AAPL** trading logic is being processed.

The [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property is used to identify which Bars object is calling the **OnBarUpdate()** method. This allows you to filter out the events that you are looking for.

Continuing our example above, let's take a closer look at what is happening. Remember, we have three Bars objects working in our script, a primary Bars **MSFT** 1 minute, an **MSFT** 3 minute, and an **AAPL** 1 minute.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        if (Close[0] > Open[0])
            // Do something
    }

    // Checks if OnBarUpdate() is called from an update on **MSFT** 3 minute Bars
    if (BarsInProgress == 1)
    {
        if (Close[0] > Open[0])
            // Do something
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars
    if (BarsInProgress == 2)
    {
        if (Close[0] > Open[0])
            // Do something
    }
}

```

What is important to understand in the above sample code is that we have "if" branches that check to see what Bars object is calling the **OnBarUpdate()** method in order to process relevant trading logic. If we only wanted to process the events from the primary Bars we could add the following condition at the top of the **OnBarUpdate()** method:

```jsx-150469391 csharp
if (BarsInProgress != 0)
    return;

```

What is also important to understand is the concept of context. When the **OnBarUpdate()** method is called, it will be called within the context of the calling Bars object. This means that if the primary Bars triggers the **OnBarUpdate()** method, all indicator methods and price data will point to that Bars object's data. Notice how the statement "if (Close\[0\] > Open\[0\]" exists under each "if" branch in the code sample above. The values returned by Close\[0\] and Open\[0\] will be the close and open price values for the calling Bars object. So when the **BarsInProgress == 0** (primary Bars) the close value returned is the close price of the **MSFT** 1 minute bar. When the **BarsInProgress == 1** the close value returned is the close price of the **MSFT** 3 minute Bars object.

## Note

Notes:

- A multi-series script only processes bar update events from the primary Bars (the series the script is applied to) and any additional Bars objects the script adds itself. Additional Bars objects from a multi-series chart or from other multi-series scripts that may be running concurrently will not be processed by this multi-series script.
- If a multi-series script adds an additional Bars object that already exists on the chart, the script will use the preexisting series instead of creating a new one to conserve memory. This includes that series' [session template](https://ninjatrader.com/support/helpGuides/nt8/?using_the_trading_hours_window.htm) as applied from the chart. If the Bars object does not exist on the chart, the session template of the added Bars object will be the session template of the primary Bars object. If the primary Bars object is using the " `<use instrument="" settings="">`" session template, then the additional Bars objects will use the default session templates as defined for their particular instruments in the [Instruments](https://developer.ninjatrader.com/docs/desktop/instruments) window.

- In a multi-series script, CurrentBars starting value will be -1 until all series have processed the first bar. To ensure you have satisfied this requirement on all your Bars objects, it is recommend you start your **OnBarUpdate()** method with [CurrentBars](https://developer.ninjatrader.com/docs/desktop/currentbars) checks, as seen in the code sample above.

- A multi-series indicator will hold the same number of data points for plots as the primary series. Setting values to plots should be done in the primary series in **OnBarUpdate()**. If you are using calculations based off of a larger secondary series, it may plot like a step ladder because there are more data points available than there are actual meaningful data values.
- The default [CloseStrategy()](https://developer.ninjatrader.com/docs/desktop/closestrategy) handling will only be applied to the primary series of a MultiSeries NinjaScript strategy.
- An indicator / strategy with multiple DataSeries of the same instrument will only process realtime **OnBarUpdate()** calls when a tick occurs in session of the trading hour templates of all added series. Any ticks not processed will be queued and processed as a tick comes in for all subsequent DataSeries.

## [Accessing the Price Data in a Multi-Bars NinjaScript](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#accessing-the-price-data-in-a-multi-bars-ninjascript)

As you probably know already, you can access the current bar's closing price with the following statement:

```jsx-1168641291 csharp
Close[0];

```

You can also access price data such as the close price of other Bars objects at any time. This is accomplished by accessing the [Opens](https://developer.ninjatrader.com/docs/desktop/opens), [Highs](https://developer.ninjatrader.com/docs/desktop/highs), [Lows](https://developer.ninjatrader.com/docs/desktop/lows), [Closes](https://developer.ninjatrader.com/docs/desktop/closes), [Volumes](https://developer.ninjatrader.com/docs/desktop/volumeseries), [Medians](https://developer.ninjatrader.com/docs/desktop/medians), [Typicals](https://developer.ninjatrader.com/docs/desktop/typicals) and [Times](https://developer.ninjatrader.com/docs/desktop/timeseries) series by index value. These properties hold collections (containers) that hold their named values for all Bars objects in a script.

Continuing with our example code above, if you wanted to access the high price of the **MSFT** 3 minute Bars object at index 1 you would write:

```jsx-1168641291 csharp
Highs[1][0];

```

This is just saying "give me the series of high prices for the Bars object at index 1 'Highs\[1\]' and return to me the current high value '\[0\]'. If the BarsInProgress index was equal to 1, the current context is of the **MSFT** 3 min Bars object so you could just write:

```jsx-1168641291 csharp
High[0];

```

The following example demonstrates various ways to access price data.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is a strategy, use BarsRequiredToTrade instead of BarsRequiredToPlot
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        double primaryClose = Close[0];
        double msft3minClose = Closes[1][0];
        double aapl1minClose = Closes[2][0];

        // primaryClose could also be expressed as
        // primaryClose = Closes[0][0];
    }

    // Checks if OnBarUpdate() is called from an update on **MSFT** 3 minute Bars object
    if (BarsInProgress == 1)
    {
        double primaryClose = Closes[0][0];
        double msft3minClose = Close[0];
        double aapl1minClose = Closes[2][0];
    }
}

```

## [Entering, Exiting and Retrieving Position Information](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments\#entering,-exiting-and-retrieving-position-information)

This section is relevant for NinjaScript strategies only. Entry and Exit methods are executed within the BarsInProgress context. Let's demonstrate with an example:

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is an indicator, use BarsRequiredToPlot instead of BarsRequiredToTrade
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0)
    {
        // Submits a buy market order for **MSFT**
        EnterLong();
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars object
    if (BarsInProgress == 2)
    {
        // Submits a buy market order for **AAPL**
        EnterLong();

        // Submits a buy market for **MSFT** when OnBarUpdate() is called for **AAPL**
        EnterLong(0, 100, "BUY MSFT");
    }
}

```

As you can see above, orders are submitted for **MSFT** when BarsInProgress is equal to 0 and for **AAPL** when BarsInProgress is equal to 2. The orders submitted are within the context of the Bars object calling the **OnBarUpdate()** method and the instrument associated to the calling Bars object. There is one exception, which is the order placed for **MSFT** within the context of the **OnBarUpdate()** call for **AAPL**. Each order method has a variation that allows you to specify the BarsInProgress index value which enables submission of orders for any instrument within the context of another instrument.

## Note

Notes:

1. Should you have multiple Bars objects of the same instrument while using Set() methods in your strategy, you should only submit orders for this instrument to the first Bars context of that instrument. This is to ensure your order logic is processed correctly and any necessary order amendments are done properly.
2. Should you have multiple Bars objects of the same instrument while using options to terminate orders/positions at the end of the session (TIF=Day or [IsExitOnSessionCloseStrategy](https://developer.ninjatrader.com/docs/desktop/isexitonsessionclosestrategy) =true), you should not submit orders to Bars objects other than the first Bars context for that instrument when on the last bar of the session. This is necessary because some of the end of session handling is applied only to the first Bars context of an instrument, and submitting orders to other Bars objects for that instrument can bypass the end-of-session handling.
3. For [advanced order methods](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling), if you DO NOT specify a BarsInProgress , the order will be submitted to the current bars in progress updating.  If the current BarsInProgress is a higher time frame, this could delay the time that the order is filled during historical backtesting.  As a result, you should always submit historical orders to the most granular of time frames.
4. When backtesting and submitting orders 'On bar close' and utilizing **OnExecutionUpdate** or **OnOrderUpdate** to submit orders, these orders will be processed immediately and filled by the fill engine depending on if the order satisfies its fill condition. This evaluation is done by looking ahead to the next bar of the current series. This is done prior to any secondary higher granularity series having a chance to run its 'OnBarUpdate' logic. If you planned on running order logic in your highest granularity added series then please insure that you submit orders in all cases to the highest granularity series.

The [Position](https://developer.ninjatrader.com/docs/desktop/position) property always references the position of the instrument of the current context. If the BarsInProgress is equal to 2 ( **AAPL** 1 minute Bars), Position would refer to the position being held for **AAPL**. The [Positions](https://developer.ninjatrader.com/docs/desktop/positions) property holds a collection of Position objects for each instrument in a strategy. Note that there is a critical difference here. Throughout this entire section we have been dealing with Bars objects. Although in our sample we have three Bars objects ( **MSFT** 1 and 3 min and **AAPL** 1 min) we only have two instruments in the strategy.

- **MSFT** position is given an index value of 0.
- **AAPL** position is given an index value of 1.

In the example below, when the **OnBarUpdate()** method is called for the primary Bars we also check if the position held for **AAPL** is NOT flat and then enter a long position in **MSFT**. The net result of this strategy is that a long position is entered for **AAPL**, and then once **AAPL** is long, we go long **MSFT**.

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Checks to ensure all Bars objects contain enough bars before beginning
    // If this is an indicator, use BarsRequiredToPlot instead of BarsRequiredToTrade
    if (CurrentBars[0] <= BarsRequiredToPlot || CurrentBars[1] <= BarsRequiredToPlot || CurrentBars[2] <= BarsRequiredToPlot)
        return;

    // Checks if OnBarUpdate() is called from an update on the primary Bars
    if (BarsInProgress == 0 && Positions[1].MarketPosition != MarketPosition.Flat)
    {
        // Submits a buy market order for **MSFT**
        EnterLong();
    }

    // Checks if OnBarUpdate() is called from an update on **AAPL** 1 minute Bars
    if (BarsInProgress == 2)
    {
        // Submits a buy market order for **AAPL**
        EnterLong();
    }
}

```