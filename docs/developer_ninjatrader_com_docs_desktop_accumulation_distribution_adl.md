## [Description](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#description)

There are many indicators available to measure volume and the flow of money for a particular stock, index or security. One of the most popular volume indicators over the years has been the Accumulation/Distribution Line. The basic premise behind volume indicators, including the Accumulation/Distribution Line, is that volume precedes price. Volume reflects the amount of shares traded in a particular stock, and is a direct reflection of the money flowing into and out of a stock. Many times before a stock advances, there will be period of increased volume just prior to the move. Most volume or money flow indicators are designed to identify early increases in positive or negative volume flow to gain an edge before the price moves. (Note: the terms "money flow" and "volume flow" are essentially interchangeable.)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#syntax)

`ADL()`

`ADL(ISeries<double> input)`

**Returns default value**

`ADL()[int barsAgo]`

`ADL(ISeries<double> input)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#parameters)

| input |
| --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Example](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#example)

```jsx-150469391 csharp
// Evaluates if ADL is rising
bool isRising = IsRising(ADL());
Print("Is ADL rising? " + isRising);

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#description)

There are many indicators available to measure volume and the flow of money for a particular stock, index or security. One of the most popular volume indicators over the years has been the Accumulation/Distribution Line. The basic premise behind volume indicators, including the Accumulation/Distribution Line, is that volume precedes price. Volume reflects the amount of shares traded in a particular stock, and is a direct reflection of the money flowing into and out of a stock. Many times before a stock advances, there will be period of increased volume just prior to the move. Most volume or money flow indicators are designed to identify early increases in positive or negative volume flow to gain an edge before the price moves. (Note: the terms "money flow" and "volume flow" are essentially interchangeable.)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#syntax)

`ADL()`

`ADL(ISeries<double> input)`

**Returns default value**

`ADL()[int barsAgo]`

`ADL(ISeries<double> input)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#parameters)

| input |
| --- |
| Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Example](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#example)

```jsx-150469391 csharp
// Evaluates if ADL is rising
bool isRising = IsRising(ADL());
Print("Is ADL rising? " + isRising);

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/accumulation_distribution_adl\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.