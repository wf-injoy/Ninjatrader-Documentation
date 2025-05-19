## [Definition](https://developer.ninjatrader.com/docs/desktop/denomination\#definition)

Indicates the currency set on an account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/denomination\#property-value)

A Currency object containing information about the currency denomination specified in the referenced account

## [Syntax](https://developer.ninjatrader.com/docs/desktop/denomination\#syntax)

`account>.Connection`

## [Examples](https://developer.ninjatrader.com/docs/desktop/denomination\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount here

        // Print myAccount's currency denomination
        NinjaTrader.Code.Output.Process("myAccount currency is set to " + myAccount.Denomination, PrintTo.OutputTab1);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/denomination\#definition)

Indicates the currency set on an account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/denomination\#property-value)

A Currency object containing information about the currency denomination specified in the referenced account

## [Syntax](https://developer.ninjatrader.com/docs/desktop/denomination\#syntax)

`account>.Connection`

## [Examples](https://developer.ninjatrader.com/docs/desktop/denomination\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount here

        // Print myAccount's currency denomination
        NinjaTrader.Code.Output.Process("myAccount currency is set to " + myAccount.Denomination, PrintTo.OutputTab1);
    }
}

```