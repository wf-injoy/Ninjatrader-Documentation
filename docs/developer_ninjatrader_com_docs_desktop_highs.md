## [Definition](https://developer.ninjatrader.com/docs/desktop/highs\#definition)

Holds an array of **ISeries `<double>`** objects holding historical bar high prices. A **ISeries `<double>`** object is added to this array when calling the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method. Its purpose is to provide access to the high prices of all Bars objects in a multi-instrument or multi-time frame script.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/highs\#property-value)

An array of **ISeries `<double>`** objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/highs\#syntax)

`Highs[int barSeriesIndex][int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/highs\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the strategy and is automatically assigned
         // a Bars object index of 1 since the primary data the strategy is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Compares the primary bar's high price to the 5-minute bar's high price
     if (Highs[0][0] > Highs[1][0])
         Print("The primary bar's high price is greater");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/highs\#definition)

Holds an array of **ISeries `<double>`** objects holding historical bar high prices. A **ISeries `<double>`** object is added to this array when calling the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method. Its purpose is to provide access to the high prices of all Bars objects in a multi-instrument or multi-time frame script.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/highs\#property-value)

An array of **ISeries `<double>`** objects.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/highs\#syntax)

`Highs[int barSeriesIndex][int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/highs\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         // Adds a 5-minute Bars object to the strategy and is automatically assigned
         // a Bars object index of 1 since the primary data the strategy is run against
         // set by the UI takes the index of 0.
         AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
     }
}

protected override void OnBarUpdate()
{
     // Compares the primary bar's high price to the 5-minute bar's high price
     if (Highs[0][0] > Highs[1][0])
         Print("The primary bar's high price is greater");
}

```