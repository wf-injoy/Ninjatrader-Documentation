## [Definition](https://developer.ninjatrader.com/docs/desktop/executionupdate\#definition)

**ExecutionUpdate** is used for subscribing to execution update events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/executionupdate\#syntax)

`ExecutionUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/executionupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to execution update events from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
    private Account account;
    public MyAddOnTab()
    {
        // Find our Sim101 account
        lock (Account.All)
            account = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to execution updates
        if (account != null)
            account.ExecutionUpdate += OnExecutionUpdate;
    }

    /* This method is fired as new executions come in, an existing execution is amended
    (e.g. by the broker's back office), or an execution is removed (e.g. by the broker's back office) */
    private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
    {
        // Output the execution
        NinjaTrader.Code.Output.Process(string.Format("Instrument: {0} Quantity: {1} Price: {2}",
            e.Execution.Instrument.FullName, e.Quantity, e.Price), PrintTo.OutputTab1);
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Make sure to unsubscribe to the execution subscription
        if (account != null)
            account.ExecutionUpdate -= OnExecutionUpdate;
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/executionupdate\#definition)

**ExecutionUpdate** is used for subscribing to execution update events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/executionupdate\#syntax)

`ExecutionUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/executionupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to execution update events from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
    private Account account;
    public MyAddOnTab()
    {
        // Find our Sim101 account
        lock (Account.All)
            account = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to execution updates
        if (account != null)
            account.ExecutionUpdate += OnExecutionUpdate;
    }

    /* This method is fired as new executions come in, an existing execution is amended
    (e.g. by the broker's back office), or an execution is removed (e.g. by the broker's back office) */
    private void OnExecutionUpdate(object sender, ExecutionEventArgs e)
    {
        // Output the execution
        NinjaTrader.Code.Output.Process(string.Format("Instrument: {0} Quantity: {1} Price: {2}",
            e.Execution.Instrument.FullName, e.Quantity, e.Price), PrintTo.OutputTab1);
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Make sure to unsubscribe to the execution subscription
        if (account != null)
            account.ExecutionUpdate -= OnExecutionUpdate;
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```