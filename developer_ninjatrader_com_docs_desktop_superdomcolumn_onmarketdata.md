## [Definition](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#definition)

Called and guaranteed to be in the correct sequence for every change in level one market data for the underlying instrument. The OnMarketData() method updates can include but is not limited to the bid, ask, last price and volume.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#syntax)

`protected override void OnMarketData(MarketDataEventArgs marketDataUpdate) { }`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#parameters)

| marketDataUpdate | A [MarketDataEventArgs](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs) representing the change in market data |

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
  if (marketDataUpdate.MarketDataType == Data.MarketDataType.Last)
  {
    // Do something
  }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#definition)

Called and guaranteed to be in the correct sequence for every change in level one market data for the underlying instrument. The OnMarketData() method updates can include but is not limited to the bid, ask, last price and volume.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#syntax)

`protected override void OnMarketData(MarketDataEventArgs marketDataUpdate) { }`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#parameters)

| marketDataUpdate | A [MarketDataEventArgs](https://developer.ninjatrader.com/docs/desktop/marketdataeventargs) representing the change in market data |

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
  if (marketDataUpdate.MarketDataType == Data.MarketDataType.Last)
  {
    // Do something
  }
}

```