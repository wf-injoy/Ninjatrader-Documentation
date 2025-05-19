## [Definition](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#definition)

Cancels all [Order](https://developer.ninjatrader.com/docs/desktop/order) of an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#syntax)

`CancelAllOrders(Instrument instrument)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#parameters)

| instrument | Instrument of the orders to be cancelled |

## [Example](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#example)

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

## [Definition](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#definition)

Cancels all [Order](https://developer.ninjatrader.com/docs/desktop/order) of an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#syntax)

`CancelAllOrders(Instrument instrument)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#parameters)

| instrument | Instrument of the orders to be cancelled |

## [Example](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders\#example)

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