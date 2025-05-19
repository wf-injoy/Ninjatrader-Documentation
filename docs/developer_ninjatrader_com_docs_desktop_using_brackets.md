In C#, square brackets represent a way to access values stored within an collection. NinjaScript comes with quite a few collections that we call ISeries objects which could be accessed with square brackets. [ISeriesT](https://developer.ninjatrader.com/docs/desktop/iseriest) objects are linked to the underlying bars series in that they hold the same number of values as the number of bars on a chart. For example, to get the close price one bar ago, you would use `Close[1]` since the value of 1 within the square brackets represents the number of bars ago whose value you wish to reference. As another example, to get the high three bars ago, you would use `High[3]`.

```jsx-150469391 csharp
double close1 = Close[1]; // gets the close price one bar ago

double high3 = High[3]; // gets the high of three bars ago

double low = Low; // results in compile error. Low is an array, and can't be accessed directly. It should be Low[n Bars ago].

```

Many of NinjaTrader's indicators store their values in Series as well, generally in a Plot. Plots are essentially a `Series<double>` object and to retrieve values from them you need to specify which value you want to access. In most cases, you'd like the current value, so you could use SMA(14)\[0\], not just SMA(14). SMA(14) is the Indicator its self or Series, and you can't access its values by calling it directly. Using SMA(14)\[0\] retrieves the part of the Series you're interested in--the most current value.

```jsx-150469391 csharp
double SMA_current = SMA(14)[0]; // gets the current value of the SMA
double SMA_1 = SMA(14)[1]; // gets the SMA value one bar ago
double SMA_value = SMA(14); // results in compile error. SMA(14) is a Series and the variable SMA_value of type double can't hold a Series.

```

Most of the time, you need an index value (number in the square brackets), but there are also cases when you need to use the ISeries instead. [CrossAbove()](https://developer.ninjatrader.com/docs/desktop/crossabove) and [CrossBelow()](https://developer.ninjatrader.com/docs/desktop/crossbelow) are two key examples. If you look at the reference page for CrossAbove(), the two method signatures (overloads) look like this:

```jsx-150469391 csharp
CrossAbove(ISeries<double> series1, ISeries<double> series2, int lookBackPeriod)

CrossAbove(ISeries<double> series1, double value, int lookBackPeriod)

```

This means the first variable must always be a `ISeries<double>` object, and the second variable can be either another `ISeries<double>` or a double value (100, 70.25, etc). To specify a `ISeries<double>` object, you can just leave off the square brackets. For example `if(CrossAbove(SMA(14), SMA(28), 1))` checks if the 14 period SMA has crossed above the 28 period SMA within the last bar. `if(CrossAbove(SMA(14)[0], SMA(28)[0], 1))` would give you a compile error because it expects a `ISeries<double>` as input, not a double value (which is returned when an index is present).

```jsx-150469391 csharp
if (CrossAbove(SMA(14), SMA(28), 1)) // works fine

if (CrossAbove(SMA(14), 1000, 1)) // works fine, this uses a double for the second argument. See the above overload.

if (CrossAbove(SMA(14)[0], SMA(28)[0], 1)) // compile error: SMA(14)[0] is a double, not a ISeries<double>

if (CrossAbove(SMA(14), SMA(28)[0], 1)) // would work fine with a ISeries<double> as first argument and a double as the second argument

```

In C#, square brackets represent a way to access values stored within an collection. NinjaScript comes with quite a few collections that we call ISeries objects which could be accessed with square brackets. [ISeriesT](https://developer.ninjatrader.com/docs/desktop/iseriest) objects are linked to the underlying bars series in that they hold the same number of values as the number of bars on a chart. For example, to get the close price one bar ago, you would use `Close[1]` since the value of 1 within the square brackets represents the number of bars ago whose value you wish to reference. As another example, to get the high three bars ago, you would use `High[3]`.

```jsx-150469391 csharp
double close1 = Close[1]; // gets the close price one bar ago

double high3 = High[3]; // gets the high of three bars ago

double low = Low; // results in compile error. Low is an array, and can't be accessed directly. It should be Low[n Bars ago].

```

Many of NinjaTrader's indicators store their values in Series as well, generally in a Plot. Plots are essentially a `Series<double>` object and to retrieve values from them you need to specify which value you want to access. In most cases, you'd like the current value, so you could use SMA(14)\[0\], not just SMA(14). SMA(14) is the Indicator its self or Series, and you can't access its values by calling it directly. Using SMA(14)\[0\] retrieves the part of the Series you're interested in--the most current value.

```jsx-150469391 csharp
double SMA_current = SMA(14)[0]; // gets the current value of the SMA
double SMA_1 = SMA(14)[1]; // gets the SMA value one bar ago
double SMA_value = SMA(14); // results in compile error. SMA(14) is a Series and the variable SMA_value of type double can't hold a Series.

```

Most of the time, you need an index value (number in the square brackets), but there are also cases when you need to use the ISeries instead. [CrossAbove()](https://developer.ninjatrader.com/docs/desktop/crossabove) and [CrossBelow()](https://developer.ninjatrader.com/docs/desktop/crossbelow) are two key examples. If you look at the reference page for CrossAbove(), the two method signatures (overloads) look like this:

```jsx-150469391 csharp
CrossAbove(ISeries<double> series1, ISeries<double> series2, int lookBackPeriod)

CrossAbove(ISeries<double> series1, double value, int lookBackPeriod)

```

This means the first variable must always be a `ISeries<double>` object, and the second variable can be either another `ISeries<double>` or a double value (100, 70.25, etc). To specify a `ISeries<double>` object, you can just leave off the square brackets. For example `if(CrossAbove(SMA(14), SMA(28), 1))` checks if the 14 period SMA has crossed above the 28 period SMA within the last bar. `if(CrossAbove(SMA(14)[0], SMA(28)[0], 1))` would give you a compile error because it expects a `ISeries<double>` as input, not a double value (which is returned when an index is present).

```jsx-150469391 csharp
if (CrossAbove(SMA(14), SMA(28), 1)) // works fine

if (CrossAbove(SMA(14), 1000, 1)) // works fine, this uses a double for the second argument. See the above overload.

if (CrossAbove(SMA(14)[0], SMA(28)[0], 1)) // compile error: SMA(14)[0] is a double, not a ISeries<double>

if (CrossAbove(SMA(14), SMA(28)[0], 1)) // would work fine with a ISeries<double> as first argument and a double as the second argument

```