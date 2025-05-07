## [Definition](https://developer.ninjatrader.com/docs/desktop/compare\#definition)

Compares two price values with respect to the Instrument **TickSize** to ensure accuracy when dealing with floating point math.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/compare\#method-return-value)

An **int** value.

- A value of "1" is returned if price1 is greater than price2.
- A value of "-1" is returned if price1 is less than price2.
- A value of "0" if price1 is equal to price2.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/compare\#syntax)

`Instrument.MasterInstrument.Compare(double price1, double price2)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/compare\#parameters)

| price1 | A **double** value representing a price. |
| price2 | A **double** value representing a price. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/compare\#examples)

```jsx-150469391 csharp
double newPrice = Close[0] + High[0] + Open[0];
if (Instrument.MasterInstrument.Compare(newPrice, Close[1]) == 1)
     // Do something since price1 is greater than price2

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/compare\#definition)

Compares two price values with respect to the Instrument **TickSize** to ensure accuracy when dealing with floating point math.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/compare\#method-return-value)

An **int** value.

- A value of "1" is returned if price1 is greater than price2.
- A value of "-1" is returned if price1 is less than price2.
- A value of "0" if price1 is equal to price2.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/compare\#syntax)

`Instrument.MasterInstrument.Compare(double price1, double price2)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/compare\#parameters)

| price1 | A **double** value representing a price. |
| price2 | A **double** value representing a price. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/compare\#examples)

```jsx-150469391 csharp
double newPrice = Close[0] + High[0] + Open[0];
if (Instrument.MasterInstrument.Compare(newPrice, Close[1]) == 1)
     // Do something since price1 is greater than price2

```