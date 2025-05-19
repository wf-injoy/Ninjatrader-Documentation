## [Description](https://developer.ninjatrader.com/docs/desktop/darvas\#description)

A trading strategy that was developed in 1956 by former ballroom dancer Nicolas Darvas. Darvas' trading technique involved buying into stocks that were trading at new 52-week highs with correspondingly high volumes.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/darvasboxtheory.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/darvas\#syntax)

`Darvas()`

`Darvas(ISeries<double> input)`

**Returns the upper value**

`Darvas().Upper[int barsAgo]`

`Darvas(ISeries<double> input).Upper[int barsAgo]`

**Returns the lower value**

`Darvas().Lower[int barsAgo]`

`Darvas(ISeries<double> input).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/darvas\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/darvas\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/darvas\#examples)

```jsx-150469391 csharp
// Prints the current upper Darvas value
double value = Darvas().Upper[0];
Print("The current upper Darvas value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/darvas\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/darvas\#description)

A trading strategy that was developed in 1956 by former ballroom dancer Nicolas Darvas. Darvas' trading technique involved buying into stocks that were trading at new 52-week highs with correspondingly high volumes.

... Courtesy of [Investopedia](http://www.investopedia.com/terms/d/darvasboxtheory.asp)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/darvas\#syntax)

`Darvas()`

`Darvas(ISeries<double> input)`

**Returns the upper value**

`Darvas().Upper[int barsAgo]`

`Darvas(ISeries<double> input).Upper[int barsAgo]`

**Returns the lower value**

`Darvas().Lower[int barsAgo]`

`Darvas(ISeries<double> input).Lower[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/darvas\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/darvas\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/darvas\#examples)

```jsx-150469391 csharp
// Prints the current upper Darvas value
double value = Darvas().Upper[0];
Print("The current upper Darvas value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/darvas\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.