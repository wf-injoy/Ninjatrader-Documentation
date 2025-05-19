The following section documents methods and properties available to every **NinjaScript** type that access various forms of data including bar data, price data, and statistical forms of data. The Common section is broken into several categories pertaining to distinct **NinjaScript** objects or concepts. An index of topics under the Common section can be found below:

| Category | Description |
| --- | --- |
| [Attributes](https://developer.ninjatrader.com/docs/desktop/attributes) | Documents both .NET native and NinjaScript custom [attributes](https://msdn.microsoft.com/en-us/library/5x6cd29c(v=vs.110).aspx) which are commonly used to define the behavior of a NinjaScript property or object |
| [Alert, Debug, Share](https://developer.ninjatrader.com/docs/desktop/alert_and_debug_concepts) | Documents methods for triggering alerts, printing debug messages, and using Share Services |
| [Analytical](https://developer.ninjatrader.com/docs/desktop/analytical) | Documents methods and properties useful for analyzing and identifying specific conditions within **Series `<t>`** collections |
| [Bars](https://developer.ninjatrader.com/docs/desktop/bars) | Represents the data returned from the historical data repository |
| [Charts](https://developer.ninjatrader.com/docs/desktop/charts) | Covers information related to accessing chart related data |
| [Drawing](https://developer.ninjatrader.com/docs/desktop/drawing) | Documents the drawing of custom shapes, lines, text and colors on your price and indicator panels from both [Indicators](https://developer.ninjatrader.com/docs/desktop/indicator) and [Strategies](https://developer.ninjatrader.com/docs/desktop/strategy) |
| [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) | Represents an instance of a [Master Instrument](https://developer.ninjatrader.com/docs/desktop/masterinstrument) |
| [ISeries `<t>`](https://developer.ninjatrader.com/docs/desktop/iseriest) | Documents the interface that is implemented by all NinjaScript classes that manage historical data as an **ISeries `<double>`** used for indicator input, and other object data |
| [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) | An event driven method which is called whenever a bar is updated |
| [OnFundamentalData()](https://developer.ninjatrader.com/docs/desktop/onfundamentaldata) | An event driven method which is called for every change in fundamental data |
| [OnMarketDepth()](https://developer.ninjatrader.com/docs/desktop/onmarketdepth) | An event driven method which is called and guaranteed to be in the correct sequence for every change in level two market data |
| [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) | An event driven method which is called whenever the script enters a new **State** |
| [SessionIterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) | An interface which allows you to traverse through various trading hours data elements which apply to a segment of bars |
| [System Indicator Methods](https://developer.ninjatrader.com/docs/desktop/indicators) | Documents syntax and return values for system indicator methods |
| [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) | Represents the Trading Hours information returned from the current bars series |
| [Name](https://developer.ninjatrader.com/docs/desktop/name) | Determines the listed name of the NinjaScript object |
| [IsVisible](https://developer.ninjatrader.com/docs/desktop/isvisible) | Determines if the current NinjaScript object should be visible on the chart |
| [DisplayName](https://developer.ninjatrader.com/docs/desktop/indicator_displayname) | Determines the text display on the chart panel |
| [Description](https://developer.ninjatrader.com/docs/desktop/description) | Text which is used on the UI's information box to be display to a user when configuration a NinjaScript object |
| [Clone()](https://developer.ninjatrader.com/docs/desktop/clone) | Used to override the default NinjaScript **Clone()** method which is called any time an instance of a NinjaScript object is created |
| [TriggerCustomEvent()](https://developer.ninjatrader.com/docs/desktop/triggercustomevent) | Provides a way to use your own custom events (such as a Timer object) so that internal NinjaScript indexes and pointers are correctly set prior to processing user code triggered by your custom event |

The following section documents methods and properties available to every **NinjaScript** type that access various forms of data including bar data, price data, and statistical forms of data. The Common section is broken into several categories pertaining to distinct **NinjaScript** objects or concepts. An index of topics under the Common section can be found below:

| Category | Description |
| --- | --- |
| [Attributes](https://developer.ninjatrader.com/docs/desktop/attributes) | Documents both .NET native and NinjaScript custom [attributes](https://msdn.microsoft.com/en-us/library/5x6cd29c(v=vs.110).aspx) which are commonly used to define the behavior of a NinjaScript property or object |
| [Alert, Debug, Share](https://developer.ninjatrader.com/docs/desktop/alert_and_debug_concepts) | Documents methods for triggering alerts, printing debug messages, and using Share Services |
| [Analytical](https://developer.ninjatrader.com/docs/desktop/analytical) | Documents methods and properties useful for analyzing and identifying specific conditions within **Series `<t>`** collections |
| [Bars](https://developer.ninjatrader.com/docs/desktop/bars) | Represents the data returned from the historical data repository |
| [Charts](https://developer.ninjatrader.com/docs/desktop/charts) | Covers information related to accessing chart related data |
| [Drawing](https://developer.ninjatrader.com/docs/desktop/drawing) | Documents the drawing of custom shapes, lines, text and colors on your price and indicator panels from both [Indicators](https://developer.ninjatrader.com/docs/desktop/indicator) and [Strategies](https://developer.ninjatrader.com/docs/desktop/strategy) |
| [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) | Represents an instance of a [Master Instrument](https://developer.ninjatrader.com/docs/desktop/masterinstrument) |
| [ISeries `<t>`](https://developer.ninjatrader.com/docs/desktop/iseriest) | Documents the interface that is implemented by all NinjaScript classes that manage historical data as an **ISeries `<double>`** used for indicator input, and other object data |
| [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) | An event driven method which is called whenever a bar is updated |
| [OnFundamentalData()](https://developer.ninjatrader.com/docs/desktop/onfundamentaldata) | An event driven method which is called for every change in fundamental data |
| [OnMarketDepth()](https://developer.ninjatrader.com/docs/desktop/onmarketdepth) | An event driven method which is called and guaranteed to be in the correct sequence for every change in level two market data |
| [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) | An event driven method which is called whenever the script enters a new **State** |
| [SessionIterator](https://developer.ninjatrader.com/docs/desktop/sessioniterator) | An interface which allows you to traverse through various trading hours data elements which apply to a segment of bars |
| [System Indicator Methods](https://developer.ninjatrader.com/docs/desktop/indicators) | Documents syntax and return values for system indicator methods |
| [TradingHours](https://developer.ninjatrader.com/docs/desktop/tradinghours) | Represents the Trading Hours information returned from the current bars series |
| [Name](https://developer.ninjatrader.com/docs/desktop/name) | Determines the listed name of the NinjaScript object |
| [IsVisible](https://developer.ninjatrader.com/docs/desktop/isvisible) | Determines if the current NinjaScript object should be visible on the chart |
| [DisplayName](https://developer.ninjatrader.com/docs/desktop/indicator_displayname) | Determines the text display on the chart panel |
| [Description](https://developer.ninjatrader.com/docs/desktop/description) | Text which is used on the UI's information box to be display to a user when configuration a NinjaScript object |
| [Clone()](https://developer.ninjatrader.com/docs/desktop/clone) | Used to override the default NinjaScript **Clone()** method which is called any time an instance of a NinjaScript object is created |
| [TriggerCustomEvent()](https://developer.ninjatrader.com/docs/desktop/triggercustomevent) | Provides a way to use your own custom events (such as a Timer object) so that internal NinjaScript indexes and pointers are correctly set prior to processing user code triggered by your custom event |