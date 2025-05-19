## [Definition](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#definition)

Prevents **OnBarUpdate** from being raised while the indicators display is not in use. Enabling this property in your indicator helps save CPU cycles while the indicator is suspended and not in use by a user. Once the indicator is in a state that would no longer be considered suspended, the historical **OnBarUpdate()** events will be triggered allowing the indicator to catch up to current real-time values.

Suspension occurs in the following scenarios:

- Minimized Chart
- Minimized Market Analyzer
- Minimized Hot List Analyzer
- Minimized SuperDOM
- Background tabs of above features are considered "minimized"
- Inactive workspaces in the background

## Note

Since events in **OnBarUpdate()** will not be processed while the indicator is suspended, internal NinjaScript functions such as [Alert](https://developer.ninjatrader.com/docs/desktop/alert), [PlaySound](https://developer.ninjatrader.com/docs/desktop/playsound), [Share](https://developer.ninjatrader.com/docs/desktop/share), [Print](https://developer.ninjatrader.com/docs/desktop/print), etc - or any other method that would be used to notify a user of activity will NOT be processed until the indicator is un-suspended.

## [Scenarios where suspension will not occur](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#scenarios-where-suspension-will-not-occur)

The **IsSuspendedWhileInactive** property will be ignored and real-time events will be processed as normal under the following cases:

- Indicators running in [Automated NinjaScript Strategies](https://ninjatrader.com/support/helpGuides/nt8/?running_a_ninjascript_strategy.htm)
- Indicators which have [manually configured alerts](https://developer.ninjatrader.com/docs/desktop/alert_debug_share)
- Indicators which have been [manually attached to orders](https://ninjatrader.com/support/helpguides/nt8/NT%20HelpGuide%20English.html?attachingorderstoindicators.htm)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#property-value)

This property returns true if indicator can take advantage of suspension optimization; otherwise, false. Default set to false.

## Note

This property is overridden to "true" automatically by the [NinjaScript Code Wizard](https://developer.ninjatrader.com/docs/desktop/ninjascript_wizard). You will need to remove the property to return to the default value or manually set it to false to disable this behavior.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#syntax)

`IsSuspendedWhileInactive`

## [Examples](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        IsSuspendedWhileInactive = true;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#definition)

Prevents **OnBarUpdate** from being raised while the indicators display is not in use. Enabling this property in your indicator helps save CPU cycles while the indicator is suspended and not in use by a user. Once the indicator is in a state that would no longer be considered suspended, the historical **OnBarUpdate()** events will be triggered allowing the indicator to catch up to current real-time values.

Suspension occurs in the following scenarios:

- Minimized Chart
- Minimized Market Analyzer
- Minimized Hot List Analyzer
- Minimized SuperDOM
- Background tabs of above features are considered "minimized"
- Inactive workspaces in the background

## Note

Since events in **OnBarUpdate()** will not be processed while the indicator is suspended, internal NinjaScript functions such as [Alert](https://developer.ninjatrader.com/docs/desktop/alert), [PlaySound](https://developer.ninjatrader.com/docs/desktop/playsound), [Share](https://developer.ninjatrader.com/docs/desktop/share), [Print](https://developer.ninjatrader.com/docs/desktop/print), etc - or any other method that would be used to notify a user of activity will NOT be processed until the indicator is un-suspended.

## [Scenarios where suspension will not occur](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#scenarios-where-suspension-will-not-occur)

The **IsSuspendedWhileInactive** property will be ignored and real-time events will be processed as normal under the following cases:

- Indicators running in [Automated NinjaScript Strategies](https://ninjatrader.com/support/helpGuides/nt8/?running_a_ninjascript_strategy.htm)
- Indicators which have [manually configured alerts](https://developer.ninjatrader.com/docs/desktop/alert_debug_share)
- Indicators which have been [manually attached to orders](https://ninjatrader.com/support/helpguides/nt8/NT%20HelpGuide%20English.html?attachingorderstoindicators.htm)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#property-value)

This property returns true if indicator can take advantage of suspension optimization; otherwise, false. Default set to false.

## Note

This property is overridden to "true" automatically by the [NinjaScript Code Wizard](https://developer.ninjatrader.com/docs/desktop/ninjascript_wizard). You will need to remove the property to return to the default value or manually set it to false to disable this behavior.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#syntax)

`IsSuspendedWhileInactive`

## [Examples](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        IsSuspendedWhileInactive = true;
    }
}

```