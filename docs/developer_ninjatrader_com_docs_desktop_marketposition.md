## [Definition](https://developer.ninjatrader.com/docs/desktop/marketposition\#definition)

Gets the account's current market position

## [Property Value](https://developer.ninjatrader.com/docs/desktop/marketposition\#property-value)

- **MarketPosition.Flat**
- **MarketPosition.Long**
- **MarketPosition.Short**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/marketposition\#syntax)

`PositionAccount.MarketPosition`

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketposition\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // If not flat print our open PnL
    if (PositionAccount.MarketPosition != MarketPosition.Flat)
        Print("Open PnL: " + PositionAccount.GetUnrealizedProfitLoss(PerformanceUnit.Points, Close[0]));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/marketposition\#definition)

Gets the account's current market position

## [Property Value](https://developer.ninjatrader.com/docs/desktop/marketposition\#property-value)

- **MarketPosition.Flat**
- **MarketPosition.Long**
- **MarketPosition.Short**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/marketposition\#syntax)

`PositionAccount.MarketPosition`

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketposition\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // If not flat print our open PnL
    if (PositionAccount.MarketPosition != MarketPosition.Flat)
        Print("Open PnL: " + PositionAccount.GetUnrealizedProfitLoss(PerformanceUnit.Points, Close[0]));
}

```