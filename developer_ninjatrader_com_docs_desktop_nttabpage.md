This is where the actual content for tabs inside the custom add on **NTWindow** can be defined.

## Note

A class derived from **NTTabPage** has to be created if instrument link or interval link functionality is desired. **IInstrumentProvider** and **IIntervalProvider** interfaces should be implemented as well to ensure proper linking.

| Method | Description |
| --- | --- |
| [Cleanup()](https://developer.ninjatrader.com/docs/desktop/cleanup) | Unregisters LinkControls and calls Cleanup() on **ICleanable** controls on the **NTTabPage** |
| [GetHeaderPart()](https://developer.ninjatrader.com/docs/desktop/getheaderpart) | Indicates the tab header name. |
| [Restore()](https://developer.ninjatrader.com/docs/desktop/restore) | Restores any elements in our **NTTabPage** from the workspace. |
| [Save()](https://developer.ninjatrader.com/docs/desktop/save) | Saves elements in our **NTTabPage** to the workspace. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/nttabpage\#examples)

```jsx-150469391 csharp
public class MyWindowTabPage : NTTabPage, NinjaTrader.Gui.Tools.IInstrumentProvider, IIntervalProvider
{
    private Instrument instrument;

    public MyWindowTabPage()
    {
        /* Define the content for our NTTabPage. We can load loose XAML to define controls and layouts
        if we so choose here as well.

        Note: XAML with event handlers defined inside WILL FAIL when attempted to load.
        Note: XAML with "inline code" WILL FAIL when attempted to load */
    }

    // Called by TabControl when a tab is being removed or window is closed
    public override void Cleanup()
    {
        /* Unsubscribe and clean up resources used by the tab that just closed. You may have
        resources you don't want to clean up just yet because the window is still being used */
    }

    // NTTabPage member. Required for determining the tab header name
    protected override string GetHeaderPart(string variable)
    {
        // Determine the text for the tab header name
        return variable;
    }

    // NTTabPage member. Required for restoring elements from workspaces
    protected override void Restore(System.Xml.Linq.XElement element)
    {
        if (element == null)
            return;

        // Restore any elements you may have saved. e.g. selected accounts or instruments
    }

    // NTTabPage member. Required for saving elements to workspaces
    protected override void Save(System.Xml.Linq.XElement element)
    {
        if (element == null)
            return;

        // Save any elements you may want persisted. e.g. selected accounts or instruments
    }

    // IInstrumentProvider member
    public Instrument Instrument
    {
        get { return instrument; }
        set
        {
            if (instrument != null)
            {
                // Unsubscribe to subscriptions to previously selected instrument
            }

            if (value != null)
            {
                // Create subscriptions for the newly selected instrument
            }

            instrument = value;

            // Update the tab header name
            RefreshHeader();
        }
    }

    // IIntervalProvider member
    public BarsPeriod BarsPeriod { get; set; }
}

```

This is where the actual content for tabs inside the custom add on **NTWindow** can be defined.

## Note

A class derived from **NTTabPage** has to be created if instrument link or interval link functionality is desired. **IInstrumentProvider** and **IIntervalProvider** interfaces should be implemented as well to ensure proper linking.

| Method | Description |
| --- | --- |
| [Cleanup()](https://developer.ninjatrader.com/docs/desktop/cleanup) | Unregisters LinkControls and calls Cleanup() on **ICleanable** controls on the **NTTabPage** |
| [GetHeaderPart()](https://developer.ninjatrader.com/docs/desktop/getheaderpart) | Indicates the tab header name. |
| [Restore()](https://developer.ninjatrader.com/docs/desktop/restore) | Restores any elements in our **NTTabPage** from the workspace. |
| [Save()](https://developer.ninjatrader.com/docs/desktop/save) | Saves elements in our **NTTabPage** to the workspace. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/nttabpage\#examples)

```jsx-150469391 csharp
public class MyWindowTabPage : NTTabPage, NinjaTrader.Gui.Tools.IInstrumentProvider, IIntervalProvider
{
    private Instrument instrument;

    public MyWindowTabPage()
    {
        /* Define the content for our NTTabPage. We can load loose XAML to define controls and layouts
        if we so choose here as well.

        Note: XAML with event handlers defined inside WILL FAIL when attempted to load.
        Note: XAML with "inline code" WILL FAIL when attempted to load */
    }

    // Called by TabControl when a tab is being removed or window is closed
    public override void Cleanup()
    {
        /* Unsubscribe and clean up resources used by the tab that just closed. You may have
        resources you don't want to clean up just yet because the window is still being used */
    }

    // NTTabPage member. Required for determining the tab header name
    protected override string GetHeaderPart(string variable)
    {
        // Determine the text for the tab header name
        return variable;
    }

    // NTTabPage member. Required for restoring elements from workspaces
    protected override void Restore(System.Xml.Linq.XElement element)
    {
        if (element == null)
            return;

        // Restore any elements you may have saved. e.g. selected accounts or instruments
    }

    // NTTabPage member. Required for saving elements to workspaces
    protected override void Save(System.Xml.Linq.XElement element)
    {
        if (element == null)
            return;

        // Save any elements you may want persisted. e.g. selected accounts or instruments
    }

    // IInstrumentProvider member
    public Instrument Instrument
    {
        get { return instrument; }
        set
        {
            if (instrument != null)
            {
                // Unsubscribe to subscriptions to previously selected instrument
            }

            if (value != null)
            {
                // Create subscriptions for the newly selected instrument
            }

            instrument = value;

            // Update the tab header name
            RefreshHeader();
        }
    }

    // IIntervalProvider member
    public BarsPeriod BarsPeriod { get; set; }
}

```