## [Historical Bid/Ask Series Overview](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#historical-bid/ask-series-overview)

NinjaTrader has the ability to use historical bid and ask price series in your NinjaScript instead of only being able to use a last price series. The following outlines the intricacies of this capability:

## Note

- You can have multiple bid/ask/last series in your NinjaScript indicator/strategy. Please use the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method to add these series to your script.

- The historical bid/ask series holds all bid/ask events sent out by the exchange. This would not be equivalent to the bid/ask at a specific time a trade went off.

- When processing your NinjaScript, the historical bid/ask series would have the historical portion triggered in the [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method only. [OnMarketData()](https://developer.ninjatrader.com/docs/desktop/onmarketdata) method events for the historical bid/ask series would only be triggered in real-time.


## Note

Tips:

- For using OnMarketData() events historically, please see the educational topic on [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).

- Changing the price type used for the primary Bars object to which a script is applied can be done in the Data Series window from any open chart.


## [Accessing Bid/Ask Series](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#accessing-bid/ask-series)

When calling [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) to add an additional [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object to your script, a constructor overload will be available which takes a MarketDataType enumeration as an argument. This will allow you to specify the price series which will be used in that particular object. If you were to pass in MarketDataType.Ask or MarketDataType.Bid, as in the example below, that particular data series will use that price type for all of its [PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries) collections, such as [Close](https://developer.ninjatrader.com/docs/desktop/close), [Open](https://developer.ninjatrader.com/docs/desktop/open), [High](https://developer.ninjatrader.com/docs/desktop/high), and [Low](https://developer.ninjatrader.com/docs/desktop/low).

## [Example](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#example)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      // Add an AAPL data series using the Ask series
      AddDataSeries("AAPL", BarsPeriodType.Minute, 30, MarketDataType.Ask);

      //Add another AAPL data series using the Bid series, with other settings identical
      AddDataSeries("AAPL", BarsPeriodType.Minute, 30, MarketDataType.Bid);
  }
}

```

## [Historical Bid/Ask Series Overview](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#historical-bid/ask-series-overview)

NinjaTrader has the ability to use historical bid and ask price series in your NinjaScript instead of only being able to use a last price series. The following outlines the intricacies of this capability:

## Note

- You can have multiple bid/ask/last series in your NinjaScript indicator/strategy. Please use the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method to add these series to your script.

- The historical bid/ask series holds all bid/ask events sent out by the exchange. This would not be equivalent to the bid/ask at a specific time a trade went off.

- When processing your NinjaScript, the historical bid/ask series would have the historical portion triggered in the [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method only. [OnMarketData()](https://developer.ninjatrader.com/docs/desktop/onmarketdata) method events for the historical bid/ask series would only be triggered in real-time.


## Note

Tips:

- For using OnMarketData() events historically, please see the educational topic on [Developing for Tick Replay](https://developer.ninjatrader.com/docs/desktop/developing_for_tick_replay).

- Changing the price type used for the primary Bars object to which a script is applied can be done in the Data Series window from any open chart.


## [Accessing Bid/Ask Series](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#accessing-bid/ask-series)

When calling [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) to add an additional [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object to your script, a constructor overload will be available which takes a MarketDataType enumeration as an argument. This will allow you to specify the price series which will be used in that particular object. If you were to pass in MarketDataType.Ask or MarketDataType.Bid, as in the example below, that particular data series will use that price type for all of its [PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries) collections, such as [Close](https://developer.ninjatrader.com/docs/desktop/close), [Open](https://developer.ninjatrader.com/docs/desktop/open), [High](https://developer.ninjatrader.com/docs/desktop/high), and [Low](https://developer.ninjatrader.com/docs/desktop/low).

## [Example](https://developer.ninjatrader.com/docs/desktop/using_historical_bid_ask_serie\#example)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.Configure)
  {
      // Add an AAPL data series using the Ask series
      AddDataSeries("AAPL", BarsPeriodType.Minute, 30, MarketDataType.Ask);

      //Add another AAPL data series using the Bid series, with other settings identical
      AddDataSeries("AAPL", BarsPeriodType.Minute, 30, MarketDataType.Bid);
  }
}

```