## [Definition](https://developer.ninjatrader.com/docs/desktop/instrument\#definition)

A tradable symbol. Represents an instance of a **Master Instrument**.

## Note

Warning: The properties in this class should NOT be accessed within the **OnStateChange()** method before the State has reached State.DataLoaded.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/instrument\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Exchange](https://developer.ninjatrader.com/docs/desktop/exchange) | Exchange of the current instrument |
| [Expiry](https://developer.ninjatrader.com/docs/desktop/expiry) | Expiration date of the futures contract |
| [FullName](https://developer.ninjatrader.com/docs/desktop/fullname) | Full name of the instrument |
| [GetInstrument()](https://developer.ninjatrader.com/docs/desktop/getinstrument) | Returns an Instrument object by the master instrument name configured in the database. |
| [MasterInstrument](https://developer.ninjatrader.com/docs/desktop/masterinstrument) | An instrument's configuration settings. These are settings and properties which are defined in the **Instrument** window. |
| FundamentalData | Instrument thread specific **FundamentalData** events |
| MarketData | Instrument thread specific **MarketData** events |
| MarketDepth | Instrument thread specific **MarketDepth** events |
| Dispatcher | A Dispatcher used for subscribing to Instrument related events. See **Multi-Threading Considerations**. |

## [Definition](https://developer.ninjatrader.com/docs/desktop/instrument\#definition)

A tradable symbol. Represents an instance of a **Master Instrument**.

## Note

Warning: The properties in this class should NOT be accessed within the **OnStateChange()** method before the State has reached State.DataLoaded.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/instrument\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Exchange](https://developer.ninjatrader.com/docs/desktop/exchange) | Exchange of the current instrument |
| [Expiry](https://developer.ninjatrader.com/docs/desktop/expiry) | Expiration date of the futures contract |
| [FullName](https://developer.ninjatrader.com/docs/desktop/fullname) | Full name of the instrument |
| [GetInstrument()](https://developer.ninjatrader.com/docs/desktop/getinstrument) | Returns an Instrument object by the master instrument name configured in the database. |
| [MasterInstrument](https://developer.ninjatrader.com/docs/desktop/masterinstrument) | An instrument's configuration settings. These are settings and properties which are defined in the **Instrument** window. |
| FundamentalData | Instrument thread specific **FundamentalData** events |
| MarketData | Instrument thread specific **MarketData** events |
| MarketDepth | Instrument thread specific **MarketDepth** events |
| Dispatcher | A Dispatcher used for subscribing to Instrument related events. See **Multi-Threading Considerations**. |