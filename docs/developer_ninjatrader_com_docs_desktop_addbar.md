## [Definition](https://developer.ninjatrader.com/docs/desktop/addbar\#definition)

Adds new data points for the Bars Type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addbar\#syntax)

`AddBar(Bars bars, double open, double high, double low, double close, DateTime time, long volume)`

`AddBar(Bars bars, double open, double high, double low, double close, DateTime time, long volume, double bid, double ask)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addbar\#parameters)

| bars | The Bars object of your bars type |
| --- | --- |
| open | A **double** value representing the open price |
| high | A **double** value representing the high price |
| low | A **double** value representing the low price |
| close | A **double** value representing the close price |
| time | A **DateTime** value representing the time |
| volume | A **long** value representing the volume |
| bid | A **double** value representing the bid price |
| ask | A **double** value representing the ask price |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addbar\#examples)

```jsx-1168641291 csharp
AddBar(bars, open, high, low, close, time, (long)Math.Min(volumeTmp, bars.BarsPeriod.Value));

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/addbar\#definition)

Adds new data points for the Bars Type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addbar\#syntax)

`AddBar(Bars bars, double open, double high, double low, double close, DateTime time, long volume)`

`AddBar(Bars bars, double open, double high, double low, double close, DateTime time, long volume, double bid, double ask)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addbar\#parameters)

| bars | The Bars object of your bars type |
| --- | --- |
| open | A **double** value representing the open price |
| high | A **double** value representing the high price |
| low | A **double** value representing the low price |
| close | A **double** value representing the close price |
| time | A **DateTime** value representing the time |
| volume | A **long** value representing the volume |
| bid | A **double** value representing the bid price |
| ask | A **double** value representing the ask price |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addbar\#examples)

```jsx-1168641291 csharp
AddBar(bars, open, high, low, close, time, (long)Math.Min(volumeTmp, bars.BarsPeriod.Value));

```