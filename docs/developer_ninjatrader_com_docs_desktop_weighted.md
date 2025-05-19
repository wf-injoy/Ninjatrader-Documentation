## [Definition](https://developer.ninjatrader.com/docs/desktop/weighted\#definition)

A collection of historical bar weighted prices. Weighted price = `(High + Low + Close + Close) / 4`.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/weighted\#property-value)

An **ISeries< `double` >** type object. Accessing this property via an index value `[int barsAgo]` returns a double value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/weighted\#syntax)

`Weighted`

`Weighted[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/weighted\#examples)

```jsx-150469391 csharp
// Current bar weighted price
double barWeigthedPrice = Weighted[0];

// Weighted price of 10 bars ago
double barWeigthedPrice = Weighted[10];

// Current bar value of a 20 period exponential moving average of weighted prices
double value = EMA(Weighted, 20)[0];

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/weighted\#definition)

A collection of historical bar weighted prices. Weighted price = `(High + Low + Close + Close) / 4`.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/weighted\#property-value)

An **ISeries< `double` >** type object. Accessing this property via an index value `[int barsAgo]` returns a double value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/weighted\#syntax)

`Weighted`

`Weighted[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/weighted\#examples)

```jsx-150469391 csharp
// Current bar weighted price
double barWeigthedPrice = Weighted[0];

// Weighted price of 10 bars ago
double barWeigthedPrice = Weighted[10];

// Current bar value of a 20 period exponential moving average of weighted prices
double value = EMA(Weighted, 20)[0];

```