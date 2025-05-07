## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#definition)

Gets the current position's average price of the specified ATM Strategy.

## Note

Changes to positions will not be reflected till at least the next **OnBarUpdate()** event after an order fill.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#method-return-value)

A **double** value representing the average price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#syntax)

`GetAtmStrategyPositionAveragePrice(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check if flat
     if (GetAtmStrategyMarketPosition("id") != MarketPosition.Flat)
         Print("Average price is " + GetAtmStrategyPositionAveragePrice("id").ToString());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#definition)

Gets the current position's average price of the specified ATM Strategy.

## Note

Changes to positions will not be reflected till at least the next **OnBarUpdate()** event after an order fill.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#method-return-value)

A **double** value representing the average price.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#syntax)

`GetAtmStrategyPositionAveragePrice(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionaverageprice\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check if flat
     if (GetAtmStrategyMarketPosition("id") != MarketPosition.Flat)
         Print("Average price is " + GetAtmStrategyPositionAveragePrice("id").ToString());
}

```