## [Definition](https://developer.ninjatrader.com/docs/desktop/ticksize\#definition)

The minimum fluctuation value which is always a value of 1-tick for the corresponding master instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/ticksize\#property-value)

A **double** value that represents the minimum fluctuation of an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ticksize\#syntax)

`TickSize`

## [Examples](https://developer.ninjatrader.com/docs/desktop/ticksize\#examples)

```jsx-150469391 csharp
// Prints the ticksize to the output window
Print("The ticksize of this instrument is " + TickSize);

// Prints the value of the current bar low less one tick size
double value = Low[0] - TickSize;
Print(value);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/ticksize\#definition)

The minimum fluctuation value which is always a value of 1-tick for the corresponding master instrument.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/ticksize\#property-value)

A **double** value that represents the minimum fluctuation of an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ticksize\#syntax)

`TickSize`

## [Examples](https://developer.ninjatrader.com/docs/desktop/ticksize\#examples)

```jsx-150469391 csharp
// Prints the ticksize to the output window
Print("The ticksize of this instrument is " + TickSize);

// Prints the value of the current bar low less one tick size
double value = Low[0] - TickSize;
Print(value);

```