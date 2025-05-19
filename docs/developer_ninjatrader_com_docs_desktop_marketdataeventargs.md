## [Definition](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#definition)

Represents a change in level one market data and is passed as a parameter in the **OnMarketData()** method.

## [Methods and Parameters](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#methods-and-parameters)

| Ask | A **double** value representing the ask price |
| Bid | A **double** value representing the bid price |
| Instrument | A Instrument object representing the instrument of the market data |
| IsReset | A bool value representing if a UI reset is needed after a manual disconnect. Note: This is only relevant for columns. Whenever this property is true, the UI needs to be reset. |
| MarketDataType | Possible values are:<br>- MarketDataType.Ask<br>- MarketDataType.Bid<br>- MarketDataType.DailyHigh<br>- MarketDataType.DailyLow<br>- MarketDataType.DailyVolume<br>- MarketDataType.Last<br>- MarketDataType.LastClose (prior session close)<br>- MarketDataType.Opening<br>- MarketDataType.OpenInterest (supported by IQFeed, Kinetick)<br>- MarketDataType.Settlement |
| Price | A **double** value representing the price |
| Time | A **DateTime** structure representing the time |
| ToString() | A string representation of the MarketDataEventArgs object |
| Volume | A long value representing volume |

## Note

Critical: If used with [TickReplay](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?tick_replay.htm), please keep in mind Tick Replay ONLY replays the Last market data event, and only stores the best inside bid/ask price at the time of the last trade event. You can think of this as the equivalent of the bid/ask price at the time a trade was reported. Please also see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).

## Note

Tips

- Not all connectivity providers support all MarketDataTypes.
- For an example of how to use IsReset please see **MarketAnalyzerColumns\\AskPrice.cs**.

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    // Print some data to the Output window
    if (marketDataUpdate.MarketDataType == MarketDataType.Last)
        Print("Last = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
    else if (marketDataUpdate.MarketDataType == MarketDataType.Ask)
        Print("Ask = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
    else if (marketDataUpdate.MarketDataType == MarketDataType.Bid)
        Print("Bid = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#definition)

Represents a change in level one market data and is passed as a parameter in the **OnMarketData()** method.

## [Methods and Parameters](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#methods-and-parameters)

| Ask | A **double** value representing the ask price |
| Bid | A **double** value representing the bid price |
| Instrument | A Instrument object representing the instrument of the market data |
| IsReset | A bool value representing if a UI reset is needed after a manual disconnect. Note: This is only relevant for columns. Whenever this property is true, the UI needs to be reset. |
| MarketDataType | Possible values are:<br>- MarketDataType.Ask<br>- MarketDataType.Bid<br>- MarketDataType.DailyHigh<br>- MarketDataType.DailyLow<br>- MarketDataType.DailyVolume<br>- MarketDataType.Last<br>- MarketDataType.LastClose (prior session close)<br>- MarketDataType.Opening<br>- MarketDataType.OpenInterest (supported by IQFeed, Kinetick)<br>- MarketDataType.Settlement |
| Price | A **double** value representing the price |
| Time | A **DateTime** structure representing the time |
| ToString() | A string representation of the MarketDataEventArgs object |
| Volume | A long value representing volume |

## Note

Critical: If used with [TickReplay](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?tick_replay.htm), please keep in mind Tick Replay ONLY replays the Last market data event, and only stores the best inside bid/ask price at the time of the last trade event. You can think of this as the equivalent of the bid/ask price at the time a trade was reported. Please also see [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).

## Note

Tips

- Not all connectivity providers support all MarketDataTypes.
- For an example of how to use IsReset please see **MarketAnalyzerColumns\\AskPrice.cs**.

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    // Print some data to the Output window
    if (marketDataUpdate.MarketDataType == MarketDataType.Last)
        Print("Last = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
    else if (marketDataUpdate.MarketDataType == MarketDataType.Ask)
        Print("Ask = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
    else if (marketDataUpdate.MarketDataType == MarketDataType.Bid)
        Print("Bid = " + marketDataUpdate.Price + " " + marketDataUpdate.Volume);
}

```