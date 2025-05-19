## [Definition](https://developer.ninjatrader.com/docs/desktop/typical\#definition)

A collection of historical bar typical prices. Typical price = (High + Low + Close) / 3.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/typical\#property-value)

An **ISeries< `double` >** type object. Accessing this property via an index value `[int barsAgo]` returns a double value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/typical\#syntax)

`Typical`

`Typical[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/typical\#examples)

```jsx-150469391 csharp
// Current bar typical price
double barTypicalPrice = Typical[0];

// Typical price of 10 bars ago
double barTypicalPrice = Typical[10];

// Current bar value of a 20 period exponential moving average of typical prices
double value = EMA(Typical, 20)[0];

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/typical\#definition)

A collection of historical bar typical prices. Typical price = (High + Low + Close) / 3.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/typical\#property-value)

An **ISeries< `double` >** type object. Accessing this property via an index value `[int barsAgo]` returns a double value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/typical\#syntax)

`Typical`

`Typical[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/typical\#examples)

```jsx-150469391 csharp
// Current bar typical price
double barTypicalPrice = Typical[0];

// Typical price of 10 bars ago
double barTypicalPrice = Typical[10];

// Current bar value of a 20 period exponential moving average of typical prices
double value = EMA(Typical, 20)[0];

```