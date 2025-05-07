## [Description](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#description)

Developed by Donald Dorsey, the Relative Volatility Index is the **RSI** using the standard deviation over the indicator period in place of the daily price change. The RVI measures the direction of volatility on a scale from 0 to 100. Readings below 50 indicate that the direction of volatility is to the downside and that you should be looking to sell, readings above 50 indicate that the direction of volatility is to the upside and that you should be looking to buy.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#syntax)

`RVI(int period)`

`RVI(ISeries<double> input, int period)`

**Returns default value**

`RVI(int period)[int barsAgo]`

`RVI[ISeries<double> input, int period)[int barsAgo]`\
\
## [Return Value](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#return-value)\
\
**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.\
\
## [Parameters](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#parameters)\
\
| Parameter | Description |\
| --- | --- |\
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |\
| period | Number of bars used in the calculation |\
\
## [Examples](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#examples)\
\
```jsx-150469391 csharp\
// OnBarUpdate method\
protected override void OnBarUpdate()\
{\
    // Check for buy condition\
    if (RVI(14)[0] > 50 && CrossAbove(SMA(9), SMA(14), 1))\
    {\
        EnterLong();\
    }\
}\
\
```\
\
## [Source Code](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#source-code)\
\
You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.\
\
## [Description](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#description)\
\
Developed by Donald Dorsey, the Relative Volatility Index is the **RSI** using the standard deviation over the indicator period in place of the daily price change. The RVI measures the direction of volatility on a scale from 0 to 100. Readings below 50 indicate that the direction of volatility is to the downside and that you should be looking to sell, readings above 50 indicate that the direction of volatility is to the upside and that you should be looking to buy.\
\
## [Syntax](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#syntax)\
\
`RVI(int period)`\
\
`RVI(ISeries<double> input, int period)`\
\
**Returns default value**\
\
`RVI(int period)[int barsAgo]`\
\
`RVI[ISeries<double> input, int period)[int barsAgo]`\
\
## [Return Value](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#return-value)\
\
**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.\
\
## [Parameters](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#parameters)\
\
| Parameter | Description |\
| --- | --- |\
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |\
| period | Number of bars used in the calculation |\
\
## [Examples](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#examples)\
\
```jsx-150469391 csharp\
// OnBarUpdate method\
protected override void OnBarUpdate()\
{\
    // Check for buy condition\
    if (RVI(14)[0] > 50 && CrossAbove(SMA(9), SMA(14), 1))\
    {\
        EnterLong();\
    }\
}\
\
```\
\
## [Source Code](https://developer.ninjatrader.com/docs/desktop/relative_volatility_index_rvi\#source-code)\
\
You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.