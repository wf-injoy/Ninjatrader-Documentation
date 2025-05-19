## [Description](https://developer.ninjatrader.com/docs/desktop/psychological_line\#description)

The Psychological Line is the ratio of the number of rising bars over the specified number of bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/psychological_line\#syntax)

`PsychologicalLine(int period)`

`PsychologicalLine(ISeries<double> input, int period)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/psychological_line\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/psychological_line\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/psychological_line\#examples)

```jsx-150469391 csharp
// Prints the current value of a 10 period Psychological Line
double value = PsychologicalLine(10)[0];
Print("The current Psychological Line value is " + value.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/psychological_line\#description)

The Psychological Line is the ratio of the number of rising bars over the specified number of bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/psychological_line\#syntax)

`PsychologicalLine(int period)`

`PsychologicalLine(ISeries<double> input, int period)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/psychological_line\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/psychological_line\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/psychological_line\#examples)

```jsx-150469391 csharp
// Prints the current value of a 10 period Psychological Line
double value = PsychologicalLine(10)[0];
Print("The current Psychological Line value is " + value.ToString());

```