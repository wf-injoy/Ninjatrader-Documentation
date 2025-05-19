## [Description](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#description)

Returns the [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) object for the specified Trading Hours template name, such as "CME US Index Futures RTH"

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#method-return-value)

A [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) object representing the specified Trading Hours template name.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#syntax)

`Get(string name)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#parameters)

| name | The name of the desired TradingHours object to return |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#examples)

```jsx-150469391 csharp
// Loop through and print all regular holidays in the found TradingHours object
foreach(KeyValuePair<DateTime, string> holiday in TradingHours.Get("CME US Index Futures RTH").Holidays)
{
  Print(String.Format("Date: {0} Description: {1}", holiday.Key, holiday.Value));
}

```

## [Description](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#description)

Returns the [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) object for the specified Trading Hours template name, such as "CME US Index Futures RTH"

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#method-return-value)

A [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) object representing the specified Trading Hours template name.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#syntax)

`Get(string name)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#parameters)

| name | The name of the desired TradingHours object to return |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tradinghoursget\#examples)

```jsx-150469391 csharp
// Loop through and print all regular holidays in the found TradingHours object
foreach(KeyValuePair<DateTime, string> holiday in TradingHours.Get("CME US Index Futures RTH").Holidays)
{
  Print(String.Format("Date: {0} Description: {1}", holiday.Key, holiday.Value));
}

```