## [Definition](https://developer.ninjatrader.com/docs/desktop/marketdepth\#definition)

**MarketDepth** can be used to access snapshot market depth and for subscribing to market depth events.

## Note

1. Remember to unsubscribe if you are no longer using the subscription.
2. You should only unsubscribe to a market depth event if you are actually subscribed.
3. You must unsubscribe from the same thread where the subscription is made. It is therefore recommended to use an [**Instrument's**](https://developer.ninjatrader.com/docs/desktop/instrument) Dispatcher to ensure this is handled properly.

## [Properties](https://developer.ninjatrader.com/docs/desktop/marketdepth\#properties)

| Property | Description |
| --- | --- |
| **Asks** | List of ask prices |
| **Bids** | List of bid prices |
| **Instrument** | [**Instrument**](https://developer.ninjatrader.com/docs/desktop/instrument) representing the instrument of the market depth event |
| **Update** | Event handler for subscribing/unsubscribing to market depth events |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/marketdepth\#syntax)

`MarketDepth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketdepth\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to market depth from an Add On. */
public class MyAddOnTab : NTTabPage
{
    private Instrument instrument;

    public MyAddOnTab()
    {
        instrument = Instrument.GetInstrument("AMD");

        if (instrument == null)
            return;

        // Follow this pattern to subscribe to MarketDepth events so they may be unsubscribed from the same instrument thread
        if (!instrument.Dispatcher.HasShutdownStarted)
            instrument.Dispatcher.InvokeAsync(() => instrument.MarketDepth.Update += OnMarketDepth);

        // Print the Ask's price ladder
        for (int i = 0; i < instrument.MarketDepth.Asks.Count; i++)
        {
            NinjaTrader.Code.Output.Process(string.Format("Position: {0} Price: {1} Volume: {2}", i,
                instrument.MarketDepth.Asks[i].Price, instrument.MarketDepth.Asks[i].Volume), PrintTo.OutputTab1);
        }
    }

    // This method is fired on market depth events and after the snapshot data is updated.
    private void OnMarketDepth(object sender, MarketDepthEventArgs e)
    {
        return;
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Follow this pattern to subscribe to MarketDepth events so they may be unsubscribed from the same instrument thread
        if (instrument != null && !instrument.Dispatcher.HasShutdownStarted)
            instrument.Dispatcher.InvokeAsync(() => instrument.MarketDepth.Update -= OnMarketDepth);
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/marketdepth\#definition)

**MarketDepth** can be used to access snapshot market depth and for subscribing to market depth events.

## Note

1. Remember to unsubscribe if you are no longer using the subscription.
2. You should only unsubscribe to a market depth event if you are actually subscribed.
3. You must unsubscribe from the same thread where the subscription is made. It is therefore recommended to use an [**Instrument's**](https://developer.ninjatrader.com/docs/desktop/instrument) Dispatcher to ensure this is handled properly.

## [Properties](https://developer.ninjatrader.com/docs/desktop/marketdepth\#properties)

| Property | Description |
| --- | --- |
| **Asks** | List of ask prices |
| **Bids** | List of bid prices |
| **Instrument** | [**Instrument**](https://developer.ninjatrader.com/docs/desktop/instrument) representing the instrument of the market depth event |
| **Update** | Event handler for subscribing/unsubscribing to market depth events |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/marketdepth\#syntax)

`MarketDepth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/marketdepth\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to market depth from an Add On. */
public class MyAddOnTab : NTTabPage
{
    private Instrument instrument;

    public MyAddOnTab()
    {
        instrument = Instrument.GetInstrument("AMD");

        if (instrument == null)
            return;

        // Follow this pattern to subscribe to MarketDepth events so they may be unsubscribed from the same instrument thread
        if (!instrument.Dispatcher.HasShutdownStarted)
            instrument.Dispatcher.InvokeAsync(() => instrument.MarketDepth.Update += OnMarketDepth);

        // Print the Ask's price ladder
        for (int i = 0; i < instrument.MarketDepth.Asks.Count; i++)
        {
            NinjaTrader.Code.Output.Process(string.Format("Position: {0} Price: {1} Volume: {2}", i,
                instrument.MarketDepth.Asks[i].Price, instrument.MarketDepth.Asks[i].Volume), PrintTo.OutputTab1);
        }
    }

    // This method is fired on market depth events and after the snapshot data is updated.
    private void OnMarketDepth(object sender, MarketDepthEventArgs e)
    {
        return;
    }

    // Called by TabControl when tab is being removed or window is closed
    public override void Cleanup()
    {
        // Follow this pattern to subscribe to MarketDepth events so they may be unsubscribed from the same instrument thread
        if (instrument != null && !instrument.Dispatcher.HasShutdownStarted)
            instrument.Dispatcher.InvokeAsync(() => instrument.MarketDepth.Update -= OnMarketDepth);
    }

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```