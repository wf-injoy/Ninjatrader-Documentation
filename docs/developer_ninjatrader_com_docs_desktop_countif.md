## [Definition](https://developer.ninjatrader.com/docs/desktop/countif\#definition)

Counts the number of instances the test condition occurs over the look-back period expressed in bars.

## Note

This method does NOT work on **multi-series** strategies and indicators.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/countif\#method-return-value)

An **int** value representing the number of occurrences found.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/countif\#syntax)

`CountIf(Func<bool> condition, int period)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/countif\#parameters)

| **condition** | A true/false expression |
| **period** | Number of bars to check for the test condition |

## Note

Tip: The syntax for the "condition" parameter uses [lambda expression](http://msdn.microsoft.com/en-us/library/bb397687.aspx) syntax.

## [Examples](https://developer.ninjatrader.com/docs/desktop/countif\#examples)

```jsx-150469391 csharp
// If in the last 10 bars we have had 8 up bars then go long
if (CountIf(() => Close[0] > Open[0], 10) > 8)
     EnterLong();

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/countif\#definition)

Counts the number of instances the test condition occurs over the look-back period expressed in bars.

## Note

This method does NOT work on **multi-series** strategies and indicators.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/countif\#method-return-value)

An **int** value representing the number of occurrences found.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/countif\#syntax)

`CountIf(Func<bool> condition, int period)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/countif\#parameters)

| **condition** | A true/false expression |
| **period** | Number of bars to check for the test condition |

## Note

Tip: The syntax for the "condition" parameter uses [lambda expression](http://msdn.microsoft.com/en-us/library/bb397687.aspx) syntax.

## [Examples](https://developer.ninjatrader.com/docs/desktop/countif\#examples)

```jsx-150469391 csharp
// If in the last 10 bars we have had 8 up bars then go long
if (CountIf(() => Close[0] > Open[0], 10) > 8)
     EnterLong();

```