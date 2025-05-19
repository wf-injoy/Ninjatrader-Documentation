## [Definition](https://developer.ninjatrader.com/docs/desktop/cancel\#definition)

Cancels specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/cancel\#syntax)

`Cancel(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/cancel\#parameters)

| orders | Order(s) to cancel |

## [Examples](https://developer.ninjatrader.com/docs/desktop/cancel\#examples)

```jsx-150469391 csharp
private Account myAccount;
Order stopOrder = null;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Cancel the stop order if an execution results in a long position
    if(e.MarketPosition == MarketPosition.Long)
        myAccount.Cancel(new[] { stopOrder });
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/cancel\#definition)

Cancels specified **Order** object(s).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/cancel\#syntax)

`Cancel(IEnumerable<` order `> orders)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/cancel\#parameters)

| orders | Order(s) to cancel |

## [Examples](https://developer.ninjatrader.com/docs/desktop/cancel\#examples)

```jsx-150469391 csharp
private Account myAccount;
Order stopOrder = null;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Cancel the stop order if an execution results in a long position
    if(e.MarketPosition == MarketPosition.Long)
        myAccount.Cancel(new[] { stopOrder });
}

```