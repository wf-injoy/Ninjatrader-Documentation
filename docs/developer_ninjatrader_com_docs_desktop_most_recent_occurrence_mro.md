## [Definition](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#definition)

Returns the number of bars ago that the test condition evaluated to true within the specified look back period expressed in bars. The **MRO()** method starts from the current bar works away (backward) from it.

## Note

This method does NOT work on [multi-series](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) strategies and indicators.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#method-return-value)

An **int** value representing the number of bars ago. Returns a value of -1 if the specified test condition did not evaluate to true within the look-back period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#syntax)

`MRO(Func<bool> condition, int instance, int lookBackPeriod)`

## Warning

1. The "instance" parameter MUST be greater than 0.
2. The "lookBackPeriod" parameter MUST be greater than 0.
3. Please check the Log tab for any other exceptions that may be thrown by the condition function parameter.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#parameters)

| Parameter | Description |
| --- | --- |
| **condition** | A true/false expression |
| **instance** | The occurrence to check for (1 is the most recent, 2 is the 2nd most recent, etc...) |
| **lookBackPeriod** | The number of bars to look back to check for the test condition. The test evaluates on the current bar and the bars within the look-back period. |

## Note

The syntax for the "condition" parameter uses [lambda expression](http://msdn.microsoft.com/en-us/library/bb397687.aspx) syntax.

## [Examples](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Prints the high price of the most recent up bar over the last 10 bars (current bar + look back period's 9 bars before that)
    int barsAgo = MRO(() => Close[0] > Open[0], 1, 9);
    if (barsAgo > -1)
        Print("The bar high was " + High[barsAgo]);
}

```

## [See Also](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#see-also)

[Least Recent Occurrence(LRO)](https://developer.ninjatrader.com/docs/desktop/least_recent_occurrence_lro)

## [Definition](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#definition)

Returns the number of bars ago that the test condition evaluated to true within the specified look back period expressed in bars. The **MRO()** method starts from the current bar works away (backward) from it.

## Note

This method does NOT work on [multi-series](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) strategies and indicators.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#method-return-value)

An **int** value representing the number of bars ago. Returns a value of -1 if the specified test condition did not evaluate to true within the look-back period.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#syntax)

`MRO(Func<bool> condition, int instance, int lookBackPeriod)`

## Warning

1. The "instance" parameter MUST be greater than 0.
2. The "lookBackPeriod" parameter MUST be greater than 0.
3. Please check the Log tab for any other exceptions that may be thrown by the condition function parameter.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#parameters)

| Parameter | Description |
| --- | --- |
| **condition** | A true/false expression |
| **instance** | The occurrence to check for (1 is the most recent, 2 is the 2nd most recent, etc...) |
| **lookBackPeriod** | The number of bars to look back to check for the test condition. The test evaluates on the current bar and the bars within the look-back period. |

## Note

The syntax for the "condition" parameter uses [lambda expression](http://msdn.microsoft.com/en-us/library/bb397687.aspx) syntax.

## [Examples](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Prints the high price of the most recent up bar over the last 10 bars (current bar + look back period's 9 bars before that)
    int barsAgo = MRO(() => Close[0] > Open[0], 1, 9);
    if (barsAgo > -1)
        Print("The bar high was " + High[barsAgo]);
}

```

## [See Also](https://developer.ninjatrader.com/docs/desktop/most_recent_occurrence_mro\#see-also)

[Least Recent Occurrence(LRO)](https://developer.ninjatrader.com/docs/desktop/least_recent_occurrence_lro)