## [Description](https://developer.ninjatrader.com/docs/desktop/range\#description)

Returns the range of a bar.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/range\#syntax)

`Range()`

`Range(ISeries<double> input)`

**Returns default value**

`Range()[int barsAgo]`

`Range(ISeries<double> input)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/range\#return-value)

**double;** Accessing this method via an index value `[int barsAgo` returns the indicator value of the referenced bar.\
\
## [Parameters](https://developer.ninjatrader.com/docs/desktop/range\#parameters)\
\
| Parameter | Description |\
| --- | --- |\
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |\
| period | Number of bars used in the calculation |\
\
## [Examples](https://developer.ninjatrader.com/docs/desktop/range\#examples)\
\
```jsx-150469391 csharp\
// Prints the range of the current bar\
double value = Range()[0];\
Print("The current bar's range is " + value.ToString());\
\
// Prints the 20 period simple moving average of range\
double value = SMA(Range(), 20)[0];\
Print("The 20 period average of range is " + value.ToString());\
\
```\
\
## [Source Code](https://developer.ninjatrader.com/docs/desktop/range\#source-code)\
\
You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.\
\
## [Description](https://developer.ninjatrader.com/docs/desktop/range\#description)\
\
Returns the range of a bar.\
\
## [Syntax](https://developer.ninjatrader.com/docs/desktop/range\#syntax)\
\
`Range()`\
\
`Range(ISeries<double> input)`\
\
**Returns default value**\
\
`Range()[int barsAgo]`\
\
`Range(ISeries<double> input)[int barsAgo]`\
\
## [Return Value](https://developer.ninjatrader.com/docs/desktop/range\#return-value)\
\
**double;** Accessing this method via an index value `[int barsAgo` returns the indicator value of the referenced bar.\
\
## [Parameters](https://developer.ninjatrader.com/docs/desktop/range\#parameters)\
\
| Parameter | Description |\
| --- | --- |\
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |\
| period | Number of bars used in the calculation |\
\
## [Examples](https://developer.ninjatrader.com/docs/desktop/range\#examples)\
\
```jsx-150469391 csharp\
// Prints the range of the current bar\
double value = Range()[0];\
Print("The current bar's range is " + value.ToString());\
\
// Prints the 20 period simple moving average of range\
double value = SMA(Range(), 20)[0];\
Print("The 20 period average of range is " + value.ToString());\
\
```\
\
## [Source Code](https://developer.ninjatrader.com/docs/desktop/range\#source-code)\
\
You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.