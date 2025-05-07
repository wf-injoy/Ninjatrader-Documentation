## [Definition](https://developer.ninjatrader.com/docs/desktop/expiry\#definition)

Indicates the expiration month of a futures contract.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/expiry\#property-value)

A **DateTime** structure representing the expiration month of a futures contract.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/expiry\#syntax)

`Instrument.Expiry`

## [Examples](https://developer.ninjatrader.com/docs/desktop/expiry\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Print the expiry of the currently configured futures instrument
   Print(String.Format("You are viewing the {0} contract", Instrument.Expiry));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/expiry\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)

## [Definition](https://developer.ninjatrader.com/docs/desktop/expiry\#definition)

Indicates the expiration month of a futures contract.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/expiry\#property-value)

A **DateTime** structure representing the expiration month of a futures contract.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/expiry\#syntax)

`Instrument.Expiry`

## [Examples](https://developer.ninjatrader.com/docs/desktop/expiry\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Print the expiry of the currently configured futures instrument
   Print(String.Format("You are viewing the {0} contract", Instrument.Expiry));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/expiry\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)