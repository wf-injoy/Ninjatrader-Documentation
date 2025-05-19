## [Definition](https://developer.ninjatrader.com/docs/desktop/account_class\#definition)

The Account class can be used to subscribe to account-related events as well as access account-related information.

## Note

Also happens when rewinding/fast forwarding Playback connections.

## [Static Account Class Properties](https://developer.ninjatrader.com/docs/desktop/account_class\#static-account-class-properties)

| Property | Description |
| --- | --- |
| **All** | A collection of Account objects |
| **[AccountStatusUpdate](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate)** | Event handler for account status updates |
| **[SimulationAccountReset](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset)** | Event handler for resets on sim accounts |

## [Methods and Properties From Account instances](https://developer.ninjatrader.com/docs/desktop/account_class\#methods-and-properties-from-account-instances)

| Property | Description |
| --- | --- |
| **[AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem)** | Represents various account variables used to reflect values the status of the account |
| **[AccountItemUpdate](https://developer.ninjatrader.com/docs/desktop/accountitemupdate)** | Event handler for changes to account values |
| **[Cancel()](https://developer.ninjatrader.com/docs/desktop/cancel)** | Cancels specified order(s) on the account |
| **[CancelAllOrders()](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders)** | Cancels all orders of an instrument on the account |
| **[Change()](https://developer.ninjatrader.com/docs/desktop/change)** | Changes specified order(s) on the account |
| **[Connection](https://developer.ninjatrader.com/docs/desktop/connection)** | A Connection representing the connection this account is associated with |
| **[CreateOrder()](https://developer.ninjatrader.com/docs/desktop/createorder)** | Creates orders for the account that need to be submitted via Submit() |
| **[Denomination](https://developer.ninjatrader.com/docs/desktop/denomination)** | A Currency representing the denomination currency of this connection |
| **[Executions](https://developer.ninjatrader.com/docs/desktop/execution)** | A collection of executions on this account |
| **[ExecutionUpdate](https://developer.ninjatrader.com/docs/desktop/executionupdate)** | Event handler for when new executions come in, an existing execution is amended, or an execution is removed |
| **[Flatten()](https://developer.ninjatrader.com/docs/desktop/flatten)** | Flattens the account on specified instrument(s) |
| **[Get()](https://developer.ninjatrader.com/docs/desktop/get)** | Returns the value of an **[AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem)** |
| **[Name](https://developer.ninjatrader.com/docs/desktop/name_account)** | A string representing the name of this account |
| **[Orders](https://developer.ninjatrader.com/docs/desktop/orders)** | A collection of orders on this account |
| **[OrderUpdate](https://developer.ninjatrader.com/docs/desktop/orderupdate)** | Event handler for changes to orders |
| **[Positions](https://developer.ninjatrader.com/docs/desktop/positions)** | A collection of positions on this account |
| **[PositionUpdate](https://developer.ninjatrader.com/docs/desktop/positionupdate)** | Event handler for changes to positions |
| **[Strategies](https://developer.ninjatrader.com/docs/desktop/strategies)** | A collection of strategies on this account |
| **[Submit()](https://developer.ninjatrader.com/docs/desktop/submit)** | Submits specified order(s) |

## [Example](https://developer.ninjatrader.com/docs/desktop/account_class\#example)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Find our Sim101 account
        lock (Account.All)
            myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to static events. Remember to unsubscribe with -= when you are done
        Account.AccountStatusUpdate += OnAccountStatusUpdate;

        if (myAccount != null)
        {
            // Print some information about our account using the AccountItem indexer
            Print(string.Format("Account Name: {0} Connection Name: {1} Cash Value {2}",
                myAccount.Name,
                myAccount.Connection.Options.Name,
                myAccount.Get(AccountItem.CashValue, Currency.UsDollar)));

            // Print the prices of the executions on our account
            lock (myAccount.Executions)
                foreach (Execution execution in myAccount.Executions)
                    Print("Price: " + execution.Price);

            // Subscribe to events. Remember to unsubscribe with -= when you are done
            myAccount.AccountItemUpdate += OnAccountItemUpdate;
            myAccount.ExecutionUpdate += OnExecutionUpdate;
        }
    }
    else if (State == State.Terminated)
    {
        // Unsubscribe to events
        myAccount.AccountItemUpdate -= OnAccountItemUpdate;
        myAccount.ExecutionUpdate -= OnExecutionUpdate;
        Account.AccountStatusUpdate -= OnAccountStatusUpdate;
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    // Do something with the account status update
}

private void OnAccountItemUpdate(object sender, AccountItemEventArgs e)
{
    // Do something with the account item update
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Do something with the execution update
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/account_class\#definition)

The Account class can be used to subscribe to account-related events as well as access account-related information.

## Note

Also happens when rewinding/fast forwarding Playback connections.

## [Static Account Class Properties](https://developer.ninjatrader.com/docs/desktop/account_class\#static-account-class-properties)

| Property | Description |
| --- | --- |
| **All** | A collection of Account objects |
| **[AccountStatusUpdate](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate)** | Event handler for account status updates |
| **[SimulationAccountReset](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset)** | Event handler for resets on sim accounts |

## [Methods and Properties From Account instances](https://developer.ninjatrader.com/docs/desktop/account_class\#methods-and-properties-from-account-instances)

| Property | Description |
| --- | --- |
| **[AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem)** | Represents various account variables used to reflect values the status of the account |
| **[AccountItemUpdate](https://developer.ninjatrader.com/docs/desktop/accountitemupdate)** | Event handler for changes to account values |
| **[Cancel()](https://developer.ninjatrader.com/docs/desktop/cancel)** | Cancels specified order(s) on the account |
| **[CancelAllOrders()](https://developer.ninjatrader.com/docs/desktop/accounts_cancelallorders)** | Cancels all orders of an instrument on the account |
| **[Change()](https://developer.ninjatrader.com/docs/desktop/change)** | Changes specified order(s) on the account |
| **[Connection](https://developer.ninjatrader.com/docs/desktop/connection)** | A Connection representing the connection this account is associated with |
| **[CreateOrder()](https://developer.ninjatrader.com/docs/desktop/createorder)** | Creates orders for the account that need to be submitted via Submit() |
| **[Denomination](https://developer.ninjatrader.com/docs/desktop/denomination)** | A Currency representing the denomination currency of this connection |
| **[Executions](https://developer.ninjatrader.com/docs/desktop/execution)** | A collection of executions on this account |
| **[ExecutionUpdate](https://developer.ninjatrader.com/docs/desktop/executionupdate)** | Event handler for when new executions come in, an existing execution is amended, or an execution is removed |
| **[Flatten()](https://developer.ninjatrader.com/docs/desktop/flatten)** | Flattens the account on specified instrument(s) |
| **[Get()](https://developer.ninjatrader.com/docs/desktop/get)** | Returns the value of an **[AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem)** |
| **[Name](https://developer.ninjatrader.com/docs/desktop/name_account)** | A string representing the name of this account |
| **[Orders](https://developer.ninjatrader.com/docs/desktop/orders)** | A collection of orders on this account |
| **[OrderUpdate](https://developer.ninjatrader.com/docs/desktop/orderupdate)** | Event handler for changes to orders |
| **[Positions](https://developer.ninjatrader.com/docs/desktop/positions)** | A collection of positions on this account |
| **[PositionUpdate](https://developer.ninjatrader.com/docs/desktop/positionupdate)** | Event handler for changes to positions |
| **[Strategies](https://developer.ninjatrader.com/docs/desktop/strategies)** | A collection of strategies on this account |
| **[Submit()](https://developer.ninjatrader.com/docs/desktop/submit)** | Submits specified order(s) |

## [Example](https://developer.ninjatrader.com/docs/desktop/account_class\#example)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Find our Sim101 account
        lock (Account.All)
            myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to static events. Remember to unsubscribe with -= when you are done
        Account.AccountStatusUpdate += OnAccountStatusUpdate;

        if (myAccount != null)
        {
            // Print some information about our account using the AccountItem indexer
            Print(string.Format("Account Name: {0} Connection Name: {1} Cash Value {2}",
                myAccount.Name,
                myAccount.Connection.Options.Name,
                myAccount.Get(AccountItem.CashValue, Currency.UsDollar)));

            // Print the prices of the executions on our account
            lock (myAccount.Executions)
                foreach (Execution execution in myAccount.Executions)
                    Print("Price: " + execution.Price);

            // Subscribe to events. Remember to unsubscribe with -= when you are done
            myAccount.AccountItemUpdate += OnAccountItemUpdate;
            myAccount.ExecutionUpdate += OnExecutionUpdate;
        }
    }
    else if (State == State.Terminated)
    {
        // Unsubscribe to events
        myAccount.AccountItemUpdate -= OnAccountItemUpdate;
        myAccount.ExecutionUpdate -= OnExecutionUpdate;
        Account.AccountStatusUpdate -= OnAccountStatusUpdate;
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    // Do something with the account status update
}

private void OnAccountItemUpdate(object sender, AccountItemEventArgs e)
{
    // Do something with the account item update
}

private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
{
    // Do something with the execution update
}

```