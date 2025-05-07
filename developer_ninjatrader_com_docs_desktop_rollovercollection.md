## [Definition](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#definition)

Indicates the rollovers that have been configured for the **Master Instrument properties** used in for futures.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#syntax)

`Bars.Instrument.MasterInstrument.RolloverCollection`

## [Property Value](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#property-value)

A **RolloversCollection** configured for the current instrument.

Possible values are:

| Parameter | Description |
| --- | --- |
| ContractMonth | A DateTime structure representing the expiry month of a futures contract |
| Date | A DateTime structure representing the date of the rollover |
| Offset | A double value representing the number of points between contracts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#examples)

```jsx-150469391 csharp
foreach(var rollover in Bars.Instrument.MasterInstrument.RolloverCollection)
{
     Print(rollover.ContractMonth);
     Print(rollover.Date);
     Print(rollover.Offset);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#definition)

Indicates the rollovers that have been configured for the **Master Instrument properties** used in for futures.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#syntax)

`Bars.Instrument.MasterInstrument.RolloverCollection`

## [Property Value](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#property-value)

A **RolloversCollection** configured for the current instrument.

Possible values are:

| Parameter | Description |
| --- | --- |
| ContractMonth | A DateTime structure representing the expiry month of a futures contract |
| Date | A DateTime structure representing the date of the rollover |
| Offset | A double value representing the number of points between contracts |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rollovercollection\#examples)

```jsx-150469391 csharp
foreach(var rollover in Bars.Instrument.MasterInstrument.RolloverCollection)
{
     Print(rollover.ContractMonth);
     Print(rollover.Date);
     Print(rollover.Offset);
}

```