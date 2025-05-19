## [Definition](https://developer.ninjatrader.com/docs/desktop/submit\#definition)

Submits specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/submit\#syntax)

`Submit(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/submit\#parameters)

| **orders** | Order(s) to submit |

## [Examples](https://developer.ninjatrader.com/docs/desktop/submit\#examples)

```jsx-150469391 csharp
Order stopOrder = null;
stopOrder = myAccount.CreateOrder(myInstrument, OrderAction.Sell, OrderType.StopMarket, TimeInForce.Day, 1, 0, 1400, "myOCO", "stopOrder", null);
myAccount.Submit(new[] { stopOrder });

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/submit\#definition)

Submits specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/submit\#syntax)

`Submit(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/submit\#parameters)

| **orders** | Order(s) to submit |

## [Examples](https://developer.ninjatrader.com/docs/desktop/submit\#examples)

```jsx-150469391 csharp
Order stopOrder = null;
stopOrder = myAccount.CreateOrder(myInstrument, OrderAction.Sell, OrderType.StopMarket, TimeInForce.Day, 1, 0, 1400, "myOCO", "stopOrder", null);
myAccount.Submit(new[] { stopOrder });

```