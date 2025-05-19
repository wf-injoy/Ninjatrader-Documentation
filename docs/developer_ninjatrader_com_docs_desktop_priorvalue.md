## [Definition](https://developer.ninjatrader.com/docs/desktop/priorvalue\#definition)

Contains the last value of **CurrentValue**. **PriorValue** is assigned the value of **CurrentValue** immediately before **CurrentValue** is updated.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/priorvalue\#property-value)

A **double** containing the last value contained in [CurrentValue](https://developer.ninjatrader.com/docs/desktop/currentvalue) before its most recent update.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/priorvalue\#syntax)

`PriorValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/priorvalue\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
   if (marketDataUpdate.MarketDataType == MarketDataType.Last)
   {
       CurrentValue = marketDataUpdate.Price;

       // Trigger an alert if the current Last price update is greater than the previous one
       if(CurrentValue > PriorValue)
           Alert("MA Alert", Priority.High, "Check Market Analyzer", "", 30, Brushes.Black, Brushes.White);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/priorvalue\#definition)

Contains the last value of **CurrentValue**. **PriorValue** is assigned the value of **CurrentValue** immediately before **CurrentValue** is updated.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/priorvalue\#property-value)

A **double** containing the last value contained in [CurrentValue](https://developer.ninjatrader.com/docs/desktop/currentvalue) before its most recent update.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/priorvalue\#syntax)

`PriorValue`

## [Examples](https://developer.ninjatrader.com/docs/desktop/priorvalue\#examples)

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
   if (marketDataUpdate.MarketDataType == MarketDataType.Last)
   {
       CurrentValue = marketDataUpdate.Price;

       // Trigger an alert if the current Last price update is greater than the previous one
       if(CurrentValue > PriorValue)
           Alert("MA Alert", Priority.High, "Check Market Analyzer", "", 30, Brushes.Black, Brushes.White);
   }
}

```