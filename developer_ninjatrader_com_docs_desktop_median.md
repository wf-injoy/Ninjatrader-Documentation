## [Definition](https://developer.ninjatrader.com/docs/desktop/median\#definition)

A collection of historical bar median prices. Median price = (High + Low) / 2.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/median\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/median\#syntax)

`Median`

`Median[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/median\#examples)

```jsx-150469391 csharp

//Current bar median price
double barMedianPrice = Median[0];

//  Median price of 10 bars ago
double barMedianPrice = Median[10];

// Current bar value of a 20 period exponential moving average of median prices
double value = EMA(Median, 20)[0];

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/median\#definition)

A collection of historical bar median prices. Median price = (High + Low) / 2.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/median\#property-value)

An **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/median\#syntax)

`Median`

`Median[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/median\#examples)

```jsx-150469391 csharp

//Current bar median price
double barMedianPrice = Median[0];

//  Median price of 10 bars ago
double barMedianPrice = Median[10];

// Current bar value of a 20 period exponential moving average of median prices
double value = EMA(Median, 20)[0];

```