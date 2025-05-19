## [Description](https://developer.ninjatrader.com/docs/desktop/correlation\#description)

The correlation indicator will plot the correlation of the data series to a desired instrument. Values close to 1 indicate movement in the same direction. Values close to -1 indicate movement in opposite directions. Values near 0 indicate no correlation.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/correlation\#syntax)

`Correlation(int period, string correlationSeries)`

`Correlation(ISeries<double> input, int period, string correlationSeries)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/correlation\#return-value)

**double**; Accessing this method via an index value **int barsAgo** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/correlation\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| correlationSeries | The data series to compare to |

## [Examples](https://developer.ninjatrader.com/docs/desktop/correlation\#examples)

```jsx-150469391 csharp
// The correlation data series must be added to OnStateChange() as this indicator runs off the correlation data series data
else if (State == State.Configure)
{
   AddDataSeries("SPY");
}

// Checks the bars in progress and prints the current correlation to the SPY
if (BarsInProgress == 0)
{
   double value = Correlation(20, "SPY")[0];
   Print("The current correlation to the SPY is " + value.ToString());
}

```

## Note

If the correlation series does not plot during a time the input series plots, a value of zero would plot in the above example. You may consider ignoring zero values.

## [Source Code](https://developer.ninjatrader.com/docs/desktop/correlation\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/correlation\#description)

The correlation indicator will plot the correlation of the data series to a desired instrument. Values close to 1 indicate movement in the same direction. Values close to -1 indicate movement in opposite directions. Values near 0 indicate no correlation.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/correlation\#syntax)

`Correlation(int period, string correlationSeries)`

`Correlation(ISeries<double> input, int period, string correlationSeries)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/correlation\#return-value)

**double**; Accessing this method via an index value **int barsAgo** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/correlation\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| correlationSeries | The data series to compare to |

## [Examples](https://developer.ninjatrader.com/docs/desktop/correlation\#examples)

```jsx-150469391 csharp
// The correlation data series must be added to OnStateChange() as this indicator runs off the correlation data series data
else if (State == State.Configure)
{
   AddDataSeries("SPY");
}

// Checks the bars in progress and prints the current correlation to the SPY
if (BarsInProgress == 0)
{
   double value = Correlation(20, "SPY")[0];
   Print("The current correlation to the SPY is " + value.ToString());
}

```

## Note

If the correlation series does not plot during a time the input series plots, a value of zero would plot in the above example. You may consider ignoring zero values.

## [Source Code](https://developer.ninjatrader.com/docs/desktop/correlation\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.