## [Definition](https://developer.ninjatrader.com/docs/desktop/exchange\#definition)

Indicates the current exchange of an instrument

## [Property Value](https://developer.ninjatrader.com/docs/desktop/exchange\#property-value)

Represents the exchange which is selected for the current instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exchange\#syntax)

`Instrument.Exchange`

## [Examples](https://developer.ninjatrader.com/docs/desktop/exchange\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Print the exchange of the currently configured instrument
    Print(String.Format("Configured instrument is on the {0} exchange", Instrument.Exchange));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/exchange\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)

## [Definition](https://developer.ninjatrader.com/docs/desktop/exchange\#definition)

Indicates the current exchange of an instrument

## [Property Value](https://developer.ninjatrader.com/docs/desktop/exchange\#property-value)

Represents the exchange which is selected for the current instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exchange\#syntax)

`Instrument.Exchange`

## [Examples](https://developer.ninjatrader.com/docs/desktop/exchange\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Print the exchange of the currently configured instrument
    Print(String.Format("Configured instrument is on the {0} exchange", Instrument.Exchange));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/exchange\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)