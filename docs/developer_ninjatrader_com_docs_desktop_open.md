## [Definition](https://developer.ninjatrader.com/docs/desktop/open\#definition)

A collection of historical bar opening prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/open\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value `[int barsAgo]` returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/open\#syntax)

`Open`

`Open[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/open\#examples)

```jsx-150469391 csharp
//Current bar opening price
double barOpenPrice = Open[0];

// Opening price of 10 bars ago
double barOpenPrice = Open[10];

//Current bar value of a 20 period simple moving average of opening prices
double value = SMA(Open, 20)[0];

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/open\#definition)

A collection of historical bar opening prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/open\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value `[int barsAgo]` returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/open\#syntax)

`Open`

`Open[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/open\#examples)

```jsx-150469391 csharp
//Current bar opening price
double barOpenPrice = Open[0];

// Opening price of 10 bars ago
double barOpenPrice = Open[10];

//Current bar value of a 20 period simple moving average of opening prices
double value = SMA(Open, 20)[0];

```