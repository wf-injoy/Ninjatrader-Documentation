## [Definition](https://developer.ninjatrader.com/docs/desktop/change\#definition)

Changes specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/change\#syntax)

`Change(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/change\#parameters)

| orders | Order(s) to change |

## [Examples](https://developer.ninjatrader.com/docs/desktop/change\#examples)

```jsx-150469391 csharp
// Example code
Order stopOrder;
stopOrder.StopPriceChanged = stopOrder.StopPrice - 4 * stopOrder.Instrument.MasterInstrument.TickSize;

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Change the stop order if an execution results in a long position
    if(e.MarketPosition == MarketPosition.Long)
        myAccount.Change(new[] { stopOrder });
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/change\#definition)

Changes specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/change\#syntax)

`Change(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/change\#parameters)

| orders | Order(s) to change |

## [Examples](https://developer.ninjatrader.com/docs/desktop/change\#examples)

```jsx-150469391 csharp
// Example code
Order stopOrder;
stopOrder.StopPriceChanged = stopOrder.StopPrice - 4 * stopOrder.Instrument.MasterInstrument.TickSize;

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Change the stop order if an execution results in a long position
    if(e.MarketPosition == MarketPosition.Long)
        myAccount.Change(new[] { stopOrder });
}

```