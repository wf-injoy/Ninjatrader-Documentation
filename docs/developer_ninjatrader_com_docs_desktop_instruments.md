## [Definition](https://developer.ninjatrader.com/docs/desktop/instruments\#definition)

A collection of **Instrument** objects currently used by a script.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/instruments\#property-value)

An array of [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/instruments\#syntax)

`Instruments[]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/instruments\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       // Print all instruments which have been loaded
       foreach (Instrument i in Instruments)
       {
           Print(i.FullName);
       }
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/instruments\#definition)

A collection of **Instrument** objects currently used by a script.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/instruments\#property-value)

An array of [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/instruments\#syntax)

`Instruments[]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/instruments\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
       // Print all instruments which have been loaded
       foreach (Instrument i in Instruments)
       {
           Print(i.FullName);
       }
   }
}

```