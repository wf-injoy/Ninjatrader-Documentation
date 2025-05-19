## [Definition](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#definition)

Cancels all orders for the specified instrument on the connection.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#syntax)

`<connection>.CancelAllOrders(Instrument instrument)`

| instrument | An Instrument object used to identify the instrument for which to cancel orders |

## [Examples](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Cancel all orders if an execution is triggered after 9pm
    if (e.Time > new DateTime(now.Year, now.Month, now.Day, 21, 0, 0))
        myAccount.CancelAllOrders(e.Execution.Instrument);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#definition)

Cancels all orders for the specified instrument on the connection.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#syntax)

`<connection>.CancelAllOrders(Instrument instrument)`

| instrument | An Instrument object used to identify the instrument for which to cancel orders |

## [Examples](https://developer.ninjatrader.com/docs/desktop/cancelallorders\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Cancel all orders if an execution is triggered after 9pm
    if (e.Time > new DateTime(now.Year, now.Month, now.Day, 21, 0, 0))
        myAccount.CancelAllOrders(e.Execution.Instrument);
}

```