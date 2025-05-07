## [Definition](https://developer.ninjatrader.com/docs/desktop/highestbar\#definition)

Returns the number of bars ago the highest price value occurred within the specified look-back period.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/highestbar\#method-return-value)

An **int** value representing a value of bars ago.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/highestbar\#syntax)

`HighestBar(ISeries<double> series, int period)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/highestbar\#parameters)

| **period** | The number of bars to include in the calculation |
| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/highestbar\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // store the highest bars ago value
   int highestBarsAgo = HighestBar(**High, Bars.BarsSinceNewTradingDay);

   //evaluate high price from highest bars ago value
   double highestPrice = High[highestBarsAgo];

   //Printed result:  Highest price of the session: 2095.5 - occurred 24 bars ago
   Print(string.Format("Highest price of the session: {0} - occurred {1} bars ago", highestPrice, highestBarsAgo));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/highestbar\#definition)

Returns the number of bars ago the highest price value occurred within the specified look-back period.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/highestbar\#method-return-value)

An **int** value representing a value of bars ago.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/highestbar\#syntax)

`HighestBar(ISeries<double> series, int period)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/highestbar\#parameters)

| **period** | The number of bars to include in the calculation |
| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/highestbar\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // store the highest bars ago value
   int highestBarsAgo = HighestBar(**High, Bars.BarsSinceNewTradingDay);

   //evaluate high price from highest bars ago value
   double highestPrice = High[highestBarsAgo];

   //Printed result:  Highest price of the session: 2095.5 - occurred 24 bars ago
   Print(string.Format("Highest price of the session: {0} - occurred {1} bars ago", highestPrice, highestBarsAgo));
}

```