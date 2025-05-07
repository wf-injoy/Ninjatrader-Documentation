## [Definition](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#definition)

Returns the type of instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#property-value)

An **InstrumentType** representing the type of an instrument.

Possible values are:

- **InstrumentType.Future**
- **InstrumentType.Stock**
- **InstrumentType.Index**
- **InstrumentType.Forex**
- **InstrumentType.Cfd**
- **InstrumentType.Cryptocurrency**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#syntax)

`Instrument.MasterInstrument.InstrumentType`

## [Examples](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#examples)

```jsx-150469391 csharp
if (Instrument.MasterInstrument.InstrumentType == InstrumentType.Future)
{
 // Do something
}
else
{
 // Do something else
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)

## [Definition](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#definition)

Returns the type of instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#property-value)

An **InstrumentType** representing the type of an instrument.

Possible values are:

- **InstrumentType.Future**
- **InstrumentType.Stock**
- **InstrumentType.Index**
- **InstrumentType.Forex**
- **InstrumentType.Cfd**
- **InstrumentType.Cryptocurrency**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#syntax)

`Instrument.MasterInstrument.InstrumentType`

## [Examples](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#examples)

```jsx-150469391 csharp
if (Instrument.MasterInstrument.InstrumentType == InstrumentType.Future)
{
 // Do something
}
else
{
 // Do something else
}

```

## [Additional Access Information](https://developer.ninjatrader.com/docs/desktop/instrumenttype\#additional-access-information)

This property can be accessed without a null reference check in the **OnBarUpdate()** event handler. When the **OnBarUpdate()** event is triggered, there will always be an **Instrument** object. Should you wish to access this property elsewhere, check for null reference first. e.g. if ( **Instrument** != null)