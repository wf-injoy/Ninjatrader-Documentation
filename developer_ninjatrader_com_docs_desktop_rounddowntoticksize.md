## [Definition](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#definition)

Returns a value that is rounded down to the nearest valid value evenly divisible by the instrument's tick size.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#method-return-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#syntax)

`Instrument.MasterInstrument.RoundDownToTickSize(double price)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#parameters)

| Parameter | Description |
| --- | --- |
| **price** | A **double** value representing a price |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#examples)

```jsx-150469391 csharp
//Takes the last 3 closes, divides them by 3, and rounds the value down to the nearest valid tick size**
Value[0] = Instrument.MasterInstrument.RoundDownToTickSize((Close[0] + Close[1] + Close[2]) / 3);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#definition)

Returns a value that is rounded down to the nearest valid value evenly divisible by the instrument's tick size.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#method-return-value)

A **double** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#syntax)

`Instrument.MasterInstrument.RoundDownToTickSize(double price)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#parameters)

| Parameter | Description |
| --- | --- |
| **price** | A **double** value representing a price |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rounddowntoticksize\#examples)

```jsx-150469391 csharp
//Takes the last 3 closes, divides them by 3, and rounds the value down to the nearest valid tick size**
Value[0] = Instrument.MasterInstrument.RoundDownToTickSize((Close[0] + Close[1] + Close[2]) / 3);

```