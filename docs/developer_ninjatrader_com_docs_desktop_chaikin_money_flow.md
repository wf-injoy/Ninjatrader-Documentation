## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#description)

The formula for **Chaikin Money Flow** is the cumulative total of the Accumulation/Distribution Values for 21 periods divided by the cumulative total of volume for 21 periods.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/chaikin-money-flow-cmf)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#syntax)

`ChaikinMoneyFlow(int period)`

`ChaikinMoneyFlow(ISeries<double> input, int period)`

**Returns default value**

`ChaikinMoneyFlow(int period)[int barsAgo]`

`ChaikinMoneyFlow(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ChaikinMoneyFlow using default price type
double value = ChaikinMoneyFlow(20)[0];
Print("The current **ChaikinMoneyFlow** value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#description)

The formula for **Chaikin Money Flow** is the cumulative total of the Accumulation/Distribution Values for 21 periods divided by the cumulative total of volume for 21 periods.

... Courtesy of [StockCharts](https://chartschool.stockcharts.com/table-of-contents/technical-indicators-and-overlays/technical-indicators/chaikin-money-flow-cmf)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#syntax)

`ChaikinMoneyFlow(int period)`

`ChaikinMoneyFlow(ISeries<double> input, int period)`

**Returns default value**

`ChaikinMoneyFlow(int period)[int barsAgo]`

`ChaikinMoneyFlow(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **period** | Number of bars used in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period ChaikinMoneyFlow using default price type
double value = ChaikinMoneyFlow(20)[0];
Print("The current **ChaikinMoneyFlow** value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chaikin_money_flow\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.