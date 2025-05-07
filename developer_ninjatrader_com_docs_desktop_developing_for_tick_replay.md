Tick Replay is used to playback 1 tick historical data to build the bars as if they had been built live. This means that tick data will be thrown as Market Data events in historical and subsequently OnMarketData and OnBarUpdate events will be called as if it was live. This provides more granular tick-related information and can be helpful if you need to know the most recent last price, last volume, best ask price, or best bid price that occurred on historical data during the bar. An indicator or strategy running Tick Replay needs to have been specifically designed to take advantage of Tick Replay. In general, this means adding additional logic to the **OnMarketData()** event handler; however, Tick Replay can also be used to call **OnBarUpdate()**, **OnEachTick**, or **OnPriceChange** during historical calculations.

## [How to Enable Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#how-to-enable-tick-replay)

To enable tick replay, it must be manually enabled on the primary [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) and the option to allow this mode is hidden by default. The option to allow for Tick Replay is located in Tools > Options > Market Data > "Show Tick Replay". The reason why it is hidden by default is that the tick replay engine utilizes 1 tick data to build historical bars. Tick Replay can generate thousands of events per bar and may take an excessive amount of time to load. It is recommended to optimize your indicators that you plan to calculate on such data by only running them in Calculate On Bar Close mode or reducing the amount of data to load to the minimum amount of data required. Since bars are built with tick data, you will only be able to build bars back as far as your historical data provider allows download of tick data.

## [How the Tick Replay Engine Works](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#how-the-tick-replay-engine-works)

Tick Replay guarantees an exact sequence of stored events are played back for both the **OnBarUpdate** and **OnMarketData** events. This mode also ensures the **OnMarketData** event is called after every **OnBarUpdate** event used to build the current bar. Consider the following examples with Tick Replay enabled on a 5-tick input series; each box is when each event occurs during Tick Replay simulation.

As you can see from the table above, the Calculate setting will have a varying degree of impact on how your indicator or strategies **OnBarUpdate** event is raised. This process repeats for every historical bar on the chart and would continue as the indicator or strategy transitions to real-time data.

## [Accessing the current best bid and ask at the time of a trade](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#accessing-the-current-best-bid-and-ask-at-the-time-of-a-trade)

NinjaTrader stores the best bid price and best ask price as the last trade occurs during the **MarketDataType.Last** event and provides it per the table below:

| marketDataUpdate.Price | The current market data price of the last trade event |
| --- | --- |
| marketDataUpdate.Ask | The current asking price at the time of the last trade event |
| marketDataUpdate.Bid | The current bidding price at the time of the last trade event |
| marketDataUpdate.Volume | The current market data volume of the last trade event |
| marketDataUpdate.Time | The current time of the last trade event |

An example below shows how to access historical Bid and Ask prices with Tick Replay:

### Accessing the current best bid and ask at the time of a trade

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    // TickReplay events only occur on the "Last" market data type
    if (marketDataUpdate.MarketDataType == MarketDataType.Last)
    {
        if (marketDataUpdate.Price >= marketDataUpdate.Ask)
        {
            Print(marketDataUpdate.Volume + " contracts traded at asking price " + marketDataUpdate.Ask);
        }
        else if (marketDataUpdate.Price <= marketDataUpdate.Bid)
        {
            Print(marketDataUpdate.Volume + " Contracts Traded at bidding price " + marketDataUpdate.Bid);
        }
    }
}

```

## [Calling a Tick Replay indicator from another Indicator or Strategy](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#calling-a-tick-replay-indicator-from-another-indicator-or-strategy)

A hosting indicator or strategy must be aware of the requirement to run through another indicator's historical Tick Replay data before it reaches **State.Historical**. To achieve desired results, you either need to store the reference in **State.DataLoaded** or (for a strategy) you can call **AddChartIndicator()**. Either approach ensures that the hosting indicator or strategy is aware of the requirements to process Tick Replay during its **State.Historical** mode and helps to ensure that the hosted indicator calculates as designed up to its current bar using Tick Replay. Please see the example below:

### Calling a Tick Replay indicator from another Indicator or Strategy

```jsx-150469391 csharp
TickReplayIndicator myTickReplayIndicator = null;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "TestHost";
    }
    else if (State == State.DataLoaded)
    {
        // Store a reference to the Tick Replay indicator before State.Historical
        // Doing so ensures the hosted indicator will run through Tick Replay
        myTickReplayIndicator = TickReplayIndicator();

        // For a strategy, you can just call AddChartIndicator(TickReplayIndicator());
        // However this also adds a copy of the indicator to the chart, which may or may not be desired
        // For calculation purposes only, storing the reference should all that needs to be required.
    }
}

protected override void OnBarUpdate()
{
    // Access the stored reference which calculates through
    // historical Tick Replay data and print the value as expected
    Print(myTickReplayIndicator[0]);
}

```

## Note

1. Tick Replay was NOT designed to provide accuracy in backtesting concerning order fills and execution and should NOT be used to expect the exact sequence of executions as running a strategy on live data. For greater order-fill resolution and accuracy in strategy backtesting, you can use the [High Fill Resolution in the Strategy Analyzer](https://ninjatrader.com/support/helpguides/nt8/?understanding_historical_fill_.htm). Furthermore, you cannot combine both Tick Replay and High Order Fill resolution.
2. If the data provided has no bid/ask data tied to the last tick data, NinjaTrader substitutes the bid/ask data for consistent user experience purposes (i.e., Bid = Last price, Ask = Bid + 1 tick). For a list of providers who support tick replay, please see the table from [Understanding the data provided by your connectivity provider](https://ninjatrader.com/support/helpGuides/nt8/data_by_provider.htm). Only bid and ask price is made available; bid and ask volume is NOT available.
3. Tick Replay ONLY replays the Last market data event and only stores the best inside bid/ask price at the time of the last trade event. You can think of this as the equivalent of the bid/ask price at the time a trade was reported. As such, historical bid/ask market data events (i.e., bid/ask volume) DO NOT work with Tick Replay. To obtain those values, you need to use a [historical bid/ask series](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie) separately from Tick Replay through **OnBarUpdate()**.
4. Tick Replay data is accessed via the **MarketDataEventArgs** object passed into **OnMarketData()** events, rather than attempting to access it via **GetCurrentAsk()** and **GetCurrentBid()**, which are methods designed to function on real-time data only.
5. Due to the nature of how some unique bars build, Tick Replay is NOT available for all bar types. For example, the default Renko and LineBreak bars which use **RemoveLastBar()** are not compatible with Tick Replay. Other custom bar types which use similar methods encounter the same limitation.
6. Tick Replay is forced for all series loaded, and there is NOT any method to reduce the number of calculations on a per series basis. In other words, you cannot mix and match tick replay series with non-tick replay series.
7. Tick Replay was only designed to work with **MarketDataType.Last**. A TickReplay indicator or strategy should NOT be mixed with a **MarketDataType.Ask** or **MarketDataType.Bid** series.
8. Tick Replay is not compatible with most Multi-Time Frame / Multi Instrument indicators, as there could be series synchronization issues leading to unexpected results.

Tick Replay is used to playback 1 tick historical data to build the bars as if they had been built live. This means that tick data will be thrown as Market Data events in historical and subsequently OnMarketData and OnBarUpdate events will be called as if it was live. This provides more granular tick-related information and can be helpful if you need to know the most recent last price, last volume, best ask price, or best bid price that occurred on historical data during the bar. An indicator or strategy running Tick Replay needs to have been specifically designed to take advantage of Tick Replay. In general, this means adding additional logic to the **OnMarketData()** event handler; however, Tick Replay can also be used to call **OnBarUpdate()**, **OnEachTick**, or **OnPriceChange** during historical calculations.

## [How to Enable Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#how-to-enable-tick-replay)

To enable tick replay, it must be manually enabled on the primary [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) and the option to allow this mode is hidden by default. The option to allow for Tick Replay is located in Tools > Options > Market Data > "Show Tick Replay". The reason why it is hidden by default is that the tick replay engine utilizes 1 tick data to build historical bars. Tick Replay can generate thousands of events per bar and may take an excessive amount of time to load. It is recommended to optimize your indicators that you plan to calculate on such data by only running them in Calculate On Bar Close mode or reducing the amount of data to load to the minimum amount of data required. Since bars are built with tick data, you will only be able to build bars back as far as your historical data provider allows download of tick data.

## [How the Tick Replay Engine Works](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#how-the-tick-replay-engine-works)

Tick Replay guarantees an exact sequence of stored events are played back for both the **OnBarUpdate** and **OnMarketData** events. This mode also ensures the **OnMarketData** event is called after every **OnBarUpdate** event used to build the current bar. Consider the following examples with Tick Replay enabled on a 5-tick input series; each box is when each event occurs during Tick Replay simulation.

As you can see from the table above, the Calculate setting will have a varying degree of impact on how your indicator or strategies **OnBarUpdate** event is raised. This process repeats for every historical bar on the chart and would continue as the indicator or strategy transitions to real-time data.

## [Accessing the current best bid and ask at the time of a trade](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#accessing-the-current-best-bid-and-ask-at-the-time-of-a-trade)

NinjaTrader stores the best bid price and best ask price as the last trade occurs during the **MarketDataType.Last** event and provides it per the table below:

| marketDataUpdate.Price | The current market data price of the last trade event |
| --- | --- |
| marketDataUpdate.Ask | The current asking price at the time of the last trade event |
| marketDataUpdate.Bid | The current bidding price at the time of the last trade event |
| marketDataUpdate.Volume | The current market data volume of the last trade event |
| marketDataUpdate.Time | The current time of the last trade event |

An example below shows how to access historical Bid and Ask prices with Tick Replay:

### Accessing the current best bid and ask at the time of a trade

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    // TickReplay events only occur on the "Last" market data type
    if (marketDataUpdate.MarketDataType == MarketDataType.Last)
    {
        if (marketDataUpdate.Price >= marketDataUpdate.Ask)
        {
            Print(marketDataUpdate.Volume + " contracts traded at asking price " + marketDataUpdate.Ask);
        }
        else if (marketDataUpdate.Price <= marketDataUpdate.Bid)
        {
            Print(marketDataUpdate.Volume + " Contracts Traded at bidding price " + marketDataUpdate.Bid);
        }
    }
}

```

## [Calling a Tick Replay indicator from another Indicator or Strategy](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay\#calling-a-tick-replay-indicator-from-another-indicator-or-strategy)

A hosting indicator or strategy must be aware of the requirement to run through another indicator's historical Tick Replay data before it reaches **State.Historical**. To achieve desired results, you either need to store the reference in **State.DataLoaded** or (for a strategy) you can call **AddChartIndicator()**. Either approach ensures that the hosting indicator or strategy is aware of the requirements to process Tick Replay during its **State.Historical** mode and helps to ensure that the hosted indicator calculates as designed up to its current bar using Tick Replay. Please see the example below:

### Calling a Tick Replay indicator from another Indicator or Strategy

```jsx-150469391 csharp
TickReplayIndicator myTickReplayIndicator = null;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name = "TestHost";
    }
    else if (State == State.DataLoaded)
    {
        // Store a reference to the Tick Replay indicator before State.Historical
        // Doing so ensures the hosted indicator will run through Tick Replay
        myTickReplayIndicator = TickReplayIndicator();

        // For a strategy, you can just call AddChartIndicator(TickReplayIndicator());
        // However this also adds a copy of the indicator to the chart, which may or may not be desired
        // For calculation purposes only, storing the reference should all that needs to be required.
    }
}

protected override void OnBarUpdate()
{
    // Access the stored reference which calculates through
    // historical Tick Replay data and print the value as expected
    Print(myTickReplayIndicator[0]);
}

```

## Note

1. Tick Replay was NOT designed to provide accuracy in backtesting concerning order fills and execution and should NOT be used to expect the exact sequence of executions as running a strategy on live data. For greater order-fill resolution and accuracy in strategy backtesting, you can use the [High Fill Resolution in the Strategy Analyzer](https://ninjatrader.com/support/helpguides/nt8/?understanding_historical_fill_.htm). Furthermore, you cannot combine both Tick Replay and High Order Fill resolution.
2. If the data provided has no bid/ask data tied to the last tick data, NinjaTrader substitutes the bid/ask data for consistent user experience purposes (i.e., Bid = Last price, Ask = Bid + 1 tick). For a list of providers who support tick replay, please see the table from [Understanding the data provided by your connectivity provider](https://ninjatrader.com/support/helpGuides/nt8/data_by_provider.htm). Only bid and ask price is made available; bid and ask volume is NOT available.
3. Tick Replay ONLY replays the Last market data event and only stores the best inside bid/ask price at the time of the last trade event. You can think of this as the equivalent of the bid/ask price at the time a trade was reported. As such, historical bid/ask market data events (i.e., bid/ask volume) DO NOT work with Tick Replay. To obtain those values, you need to use a [historical bid/ask series](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie) separately from Tick Replay through **OnBarUpdate()**.
4. Tick Replay data is accessed via the **MarketDataEventArgs** object passed into **OnMarketData()** events, rather than attempting to access it via **GetCurrentAsk()** and **GetCurrentBid()**, which are methods designed to function on real-time data only.
5. Due to the nature of how some unique bars build, Tick Replay is NOT available for all bar types. For example, the default Renko and LineBreak bars which use **RemoveLastBar()** are not compatible with Tick Replay. Other custom bar types which use similar methods encounter the same limitation.
6. Tick Replay is forced for all series loaded, and there is NOT any method to reduce the number of calculations on a per series basis. In other words, you cannot mix and match tick replay series with non-tick replay series.
7. Tick Replay was only designed to work with **MarketDataType.Last**. A TickReplay indicator or strategy should NOT be mixed with a **MarketDataType.Ask** or **MarketDataType.Bid** series.
8. Tick Replay is not compatible with most Multi-Time Frame / Multi Instrument indicators, as there could be series synchronization issues leading to unexpected results.