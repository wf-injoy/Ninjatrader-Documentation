## [Definition](https://developer.ninjatrader.com/docs/desktop/fullname\#definition)

Indicates the full NinjaTrader name of an instrument. For futures, this would include the expiration date. The September S&P 500 Emini contract full name is "ES 09-16".

## [Property Value](https://developer.ninjatrader.com/docs/desktop/fullname\#property-value)

A string representing the full name of the instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/fullname\#syntax)

`Instrument.FullName`

## [Examples](https://developer.ninjatrader.com/docs/desktop/fullname\#examples)

```jsx-150469391 csharp

protected override void OnBarUpdate()
{
   // Print the full name (including contract month) of the configured instrument
   Print(String.Format("{0} is being used as the input series", Instrument.FullName));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/fullname\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)

## [Definition](https://developer.ninjatrader.com/docs/desktop/fullname\#definition)

Indicates the full NinjaTrader name of an instrument. For futures, this would include the expiration date. The September S&P 500 Emini contract full name is "ES 09-16".

## [Property Value](https://developer.ninjatrader.com/docs/desktop/fullname\#property-value)

A string representing the full name of the instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/fullname\#syntax)

`Instrument.FullName`

## [Examples](https://developer.ninjatrader.com/docs/desktop/fullname\#examples)

```jsx-150469391 csharp

protected override void OnBarUpdate()
{
   // Print the full name (including contract month) of the configured instrument
   Print(String.Format("{0} is being used as the input series", Instrument.FullName));
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/fullname\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)