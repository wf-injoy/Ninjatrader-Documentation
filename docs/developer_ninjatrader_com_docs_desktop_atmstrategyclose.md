## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#definition)

Cancels any working orders and closes any open position of a strategy using the default [ATM strategy close behavior](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?closing_a_position_or_atm_stra.htm).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#method-return-value)

Returns true if the specified ATM strategy was found; otherwise false.

## Note

A method return value of true in NO WAY indicates that the strategy in fact is closed. It indicates that the the specified ATM strategy was found and the internal close routine was triggered.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#syntax)

`AtmStrategyClose(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#parameters)

| atmStrategyId | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check for valid condition and create an ATM Strategy
     if (GetAtmStrategyUnrealizedProfitLoss("idValue") > 500)
         AtmStrategyClose("idValue");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#definition)

Cancels any working orders and closes any open position of a strategy using the default [ATM strategy close behavior](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?closing_a_position_or_atm_stra.htm).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#method-return-value)

Returns true if the specified ATM strategy was found; otherwise false.

## Note

A method return value of true in NO WAY indicates that the strategy in fact is closed. It indicates that the the specified ATM strategy was found and the internal close routine was triggered.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#syntax)

`AtmStrategyClose(string atmStrategyId)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#parameters)

| atmStrategyId | The unique identifier for the ATM strategy |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyclose\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Check for valid condition and create an ATM Strategy
     if (GetAtmStrategyUnrealizedProfitLoss("idValue") > 500)
         AtmStrategyClose("idValue");
}

```