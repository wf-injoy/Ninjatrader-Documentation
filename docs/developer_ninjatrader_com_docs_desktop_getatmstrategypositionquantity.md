## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#definition)

Gets the current position quantity of the specified ATM Strategy.

## Note

Changes to positions will not be reflected till at least the next **OnBarUpdate()** event after an order fill.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#method-return-value)

An **int** value representing the quantity.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#syntax)

`GetAtmStrategyPositionQuantity(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check if flat
     if (GetAtmStrategyMarketPosition("idValue") != MarketPosition.Flat)
         Print("Position size is " + GetAtmStrategyPositionQuantity("idValue").ToString());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#definition)

Gets the current position quantity of the specified ATM Strategy.

## Note

Changes to positions will not be reflected till at least the next **OnBarUpdate()** event after an order fill.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#method-return-value)

An **int** value representing the quantity.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#syntax)

`GetAtmStrategyPositionQuantity(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#parameters)

| **atmStrategyId** | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getatmstrategypositionquantity\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check if flat
     if (GetAtmStrategyMarketPosition("idValue") != MarketPosition.Flat)
         Print("Position size is " + GetAtmStrategyPositionQuantity("idValue").ToString());
}

```