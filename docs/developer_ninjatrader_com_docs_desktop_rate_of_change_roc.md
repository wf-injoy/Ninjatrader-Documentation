## [Description](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#description)

The Rate of Change (ROC) indicator is a very simple yet effective momentum oscillator that measures the percent change in price from one period to the next. The ROC calculation compares the current price with the price n periods ago.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/rate-of-change-roc)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#syntax)

`ROC(int period)`

`ROC(ISeries<double> input, int period)`

**Returns default value**

`ROC(int period)[int barsAgo]`

`ROC(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#examples)

```jsx-150469391 csharp
Prints the current value of a 20 period ROC using default price type
double value = ROC(20)[0];
Print("The current ROC value is " + value.ToString());

// Prints the current value of a 20 period ROC using high price type
double value = ROC(High, 20)[0];
Print("The current ROC value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#description)

The Rate of Change (ROC) indicator is a very simple yet effective momentum oscillator that measures the percent change in price from one period to the next. The ROC calculation compares the current price with the price n periods ago.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/rate-of-change-roc)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#syntax)

`ROC(int period)`

`ROC(ISeries<double> input, int period)`

**Returns default value**

`ROC(int period)[int barsAgo]`

`ROC(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#parameters)

| Parameter | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#examples)

```jsx-150469391 csharp
Prints the current value of a 20 period ROC using default price type
double value = ROC(20)[0];
Print("The current ROC value is " + value.ToString());

// Prints the current value of a 20 period ROC using high price type
double value = ROC(High, 20)[0];
Print("The current ROC value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/rate_of_change_roc\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.