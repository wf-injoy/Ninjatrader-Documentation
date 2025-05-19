Creating custom Bars Types allows for incredible flexibility in the way you want to present data in a chart. The methods and properties covered in this section are unique to custom Bars Type development.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/bars_type\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AddBar()](https://developer.ninjatrader.com/docs/desktop/addbar) | Adds new data points for the Bars Type. |
| [ApplyDefaultBasePeriodValue](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue) | Sets the default base values used for the [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) selected by the user (e.g., the default PeriodValue, DaysToLoad, etc.) for your custom Bar Type. |
| [ApplyDefaultValue](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue) | Sets the default [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) values used for a custom Bar Type. |
| [BuiltFrom](https://developer.ninjatrader.com/docs/desktop/builtfrom) | Determines the base dataset used to build the BarsType (i.e., Tick, Minute, Day). |
| [GetInitialLookBackDays()](https://developer.ninjatrader.com/docs/desktop/getinitiallookbackdays) | Determines how many days of data load when a user makes a "bars back" data request. |
| [GetPercentComplete()](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete) | Determines the value your BarsType would return for [Bars.PercentComplete](https://developer.ninjatrader.com/docs/desktop/percentcomplete) |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon_barstype) | The shape which displays next to the Bars Type menu item. |
| [IsRemoveLastBarSupported](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported) | Determines if the bars type can use the [RemoveLastBar()](https://developer.ninjatrader.com/docs/desktop/removelastbar) method when true, otherwise an exception will be thrown. |
| [IsTimebased](https://developer.ninjatrader.com/docs/desktop/istimebased) | Used to indicate the BarsType is built from time-based bars (day, minute, second). |
| [OnDataPoint()](https://developer.ninjatrader.com/docs/desktop/ondatapoint) | OnDataPoint() method is where you should adjust data points (bar values) of your series through [AddBar()](https://developer.ninjatrader.com/docs/desktop/addbar) and [UpdateBar()](https://developer.ninjatrader.com/docs/desktop/updatebar). |
| [RemoveLastBar()](https://developer.ninjatrader.com/docs/desktop/removelastbar) | Removes the last data point for the Bars Type. |
| [SessionIterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) | Provides trading session information to the bars type. Must be built using the bars object. |
| [UpdateBar()](https://developer.ninjatrader.com/docs/desktop/updatebar) | Updates a data point in our Bars Type. |

Creating custom Bars Types allows for incredible flexibility in the way you want to present data in a chart. The methods and properties covered in this section are unique to custom Bars Type development.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/bars_type\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AddBar()](https://developer.ninjatrader.com/docs/desktop/addbar) | Adds new data points for the Bars Type. |
| [ApplyDefaultBasePeriodValue](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue) | Sets the default base values used for the [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) selected by the user (e.g., the default PeriodValue, DaysToLoad, etc.) for your custom Bar Type. |
| [ApplyDefaultValue](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue) | Sets the default [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) values used for a custom Bar Type. |
| [BuiltFrom](https://developer.ninjatrader.com/docs/desktop/builtfrom) | Determines the base dataset used to build the BarsType (i.e., Tick, Minute, Day). |
| [GetInitialLookBackDays()](https://developer.ninjatrader.com/docs/desktop/getinitiallookbackdays) | Determines how many days of data load when a user makes a "bars back" data request. |
| [GetPercentComplete()](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete) | Determines the value your BarsType would return for [Bars.PercentComplete](https://developer.ninjatrader.com/docs/desktop/percentcomplete) |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon_barstype) | The shape which displays next to the Bars Type menu item. |
| [IsRemoveLastBarSupported](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported) | Determines if the bars type can use the [RemoveLastBar()](https://developer.ninjatrader.com/docs/desktop/removelastbar) method when true, otherwise an exception will be thrown. |
| [IsTimebased](https://developer.ninjatrader.com/docs/desktop/istimebased) | Used to indicate the BarsType is built from time-based bars (day, minute, second). |
| [OnDataPoint()](https://developer.ninjatrader.com/docs/desktop/ondatapoint) | OnDataPoint() method is where you should adjust data points (bar values) of your series through [AddBar()](https://developer.ninjatrader.com/docs/desktop/addbar) and [UpdateBar()](https://developer.ninjatrader.com/docs/desktop/updatebar). |
| [RemoveLastBar()](https://developer.ninjatrader.com/docs/desktop/removelastbar) | Removes the last data point for the Bars Type. |
| [SessionIterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) | Provides trading session information to the bars type. Must be built using the bars object. |
| [UpdateBar()](https://developer.ninjatrader.com/docs/desktop/updatebar) | Updates a data point in our Bars Type. |