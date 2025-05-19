## [Definition](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#definition)

The **OnMarketDepth()** method is called and guaranteed to be in the correct sequence for every change in level two market data (market depth) for the underlying instrument.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#syntax)

`MarketDepth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#examples)

```jsx-150469391 csharp
protected override void OnMarketDepth(Data.MarketDepthEventArgs marketDepthUpdate)

{
    if (marketDepthUpdate.MarketDataType == MarketDataType.Ask && marketDepthUpdate.Operation == Operation.Update)
        // Do something
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#definition)

The **OnMarketDepth()** method is called and guaranteed to be in the correct sequence for every change in level two market data (market depth) for the underlying instrument.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#syntax)

`MarketDepth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth\#examples)

```jsx-150469391 csharp
protected override void OnMarketDepth(Data.MarketDepthEventArgs marketDepthUpdate)

{
    if (marketDepthUpdate.MarketDataType == MarketDataType.Ask && marketDepthUpdate.Operation == Operation.Update)
        // Do something
}

```