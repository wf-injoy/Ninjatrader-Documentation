## [Definition](https://developer.ninjatrader.com/docs/desktop/orderupdate\#definition)

**OrderUpdate** can be used for subscribing to order update events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/orderupdate\#syntax)

`OrderUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/orderupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to order update events from an Add On. The concept can be carried over to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
    private Account account;
    private Order myEntryOrder;
    private Order profitTarget;
    private Order stopLoss;

    public MyAddOnTab()
    {
        // Find our Sim101 account
        lock (Account.All)
            account = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to order updates
        if (account != null)
            account.OrderUpdate += OnOrderUpdate;
    }

    // This method is fired as the status of an order changes
    private void OnOrderUpdate(object sender, OrderEventArgs e)
    {
        // Submit stop/target bracket orders
        if (myEntryOrder != null && myEntryOrder == e.Order)
        {
            if (e.OrderState == OrderState.Filled)
            {
                string oco = Guid.NewGuid().ToString("N");

                profitTarget = account.CreateOrder(e.Order.Instrument, OrderAction.Sell, OrderType.Limit, OrderEntry.Manual, TimeInForce.Day,
                    e.Quantity, e.AverageFillPrice + 10 * e.Order.Instrument.MasterInstrument.TickSize, 0, oco, "Profit Target", Core.Globals.MaxDate, null);
                stopLoss = account.CreateOrder(e.Order.Instrument, OrderAction.Sell, OrderType.StopMarket, OrderEntry.Manual, TimeInForce.Day,
                    e.Quantity, 0, e.AverageFillPrice - 10 * e.Order.Instrument.MasterInstrument.TickSize, oco, "Stop Loss", Core.Globals.MaxDate, null);
                account.Submit(new[] { profitTarget, stopLoss });
            }
        }
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Make sure to unsubscribe to the orders subscription
        if (account != null)
            account.OrderUpdate -= OnOrderUpdate;
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/orderupdate\#definition)

**OrderUpdate** can be used for subscribing to order update events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/orderupdate\#syntax)

`OrderUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/orderupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to order update events from an Add On. The concept can be carried over to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
    private Account account;
    private Order myEntryOrder;
    private Order profitTarget;
    private Order stopLoss;

    public MyAddOnTab()
    {
        // Find our Sim101 account
        lock (Account.All)
            account = Account.All.FirstOrDefault(a => a.Name == "Sim101");

        // Subscribe to order updates
        if (account != null)
            account.OrderUpdate += OnOrderUpdate;
    }

    // This method is fired as the status of an order changes
    private void OnOrderUpdate(object sender, OrderEventArgs e)
    {
        // Submit stop/target bracket orders
        if (myEntryOrder != null && myEntryOrder == e.Order)
        {
            if (e.OrderState == OrderState.Filled)
            {
                string oco = Guid.NewGuid().ToString("N");

                profitTarget = account.CreateOrder(e.Order.Instrument, OrderAction.Sell, OrderType.Limit, OrderEntry.Manual, TimeInForce.Day,
                    e.Quantity, e.AverageFillPrice + 10 * e.Order.Instrument.MasterInstrument.TickSize, 0, oco, "Profit Target", Core.Globals.MaxDate, null);
                stopLoss = account.CreateOrder(e.Order.Instrument, OrderAction.Sell, OrderType.StopMarket, OrderEntry.Manual, TimeInForce.Day,
                    e.Quantity, 0, e.AverageFillPrice - 10 * e.Order.Instrument.MasterInstrument.TickSize, oco, "Stop Loss", Core.Globals.MaxDate, null);
                account.Submit(new[] { profitTarget, stopLoss });
            }
        }
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Make sure to unsubscribe to the orders subscription
        if (account != null)
            account.OrderUpdate -= OnOrderUpdate;
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.

```