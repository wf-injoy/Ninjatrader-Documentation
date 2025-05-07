## [Definition](https://developer.ninjatrader.com/docs/desktop/low\#definition)

A collection of historical bar low prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/low\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/low\#syntax)

`Low`

`Low[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/low\#examples)

```jsx-150469391 csharp
// Current bar low price
double barLowPrice = Low[0];

// Low price of 10 bars ago
double barLowPrice = Low[10];

// Current bar value of a 20 period exponential moving average of low prices**
double value = EMA(Low, 20)[0];

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/low\#definition)

A collection of historical bar low prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/low\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/low\#syntax)

`Low`

`Low[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/low\#examples)

```jsx-150469391 csharp
// Current bar low price
double barLowPrice = Low[0];

// Low price of 10 bars ago
double barLowPrice = Low[10];

// Current bar value of a 20 period exponential moving average of low prices**
double value = EMA(Low, 20)[0];

```