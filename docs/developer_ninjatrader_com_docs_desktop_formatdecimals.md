## [Definition](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#definition)

Rounds the value contained in **CurrentValue** to a specified number of decimal places before displaying it in the Market Analyzer column.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#property-value)

An int representing a number of decimal places to which to round **CurrentValue**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#syntax)

`FormatDecimals`

## [Examples](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Round CurrentValue to one decimal place
        FormatDecimals = 1;
    }
}

protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    CurrentValue = marketDataUpdate.Price;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#definition)

Rounds the value contained in **CurrentValue** to a specified number of decimal places before displaying it in the Market Analyzer column.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#property-value)

An int representing a number of decimal places to which to round **CurrentValue**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#syntax)

`FormatDecimals`

## [Examples](https://developer.ninjatrader.com/docs/desktop/formatdecimals\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Round CurrentValue to one decimal place
        FormatDecimals = 1;
    }
}

protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
    CurrentValue = marketDataUpdate.Price;
}

```