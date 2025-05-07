## [Definition](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#definition)

Indicates the Merge Policy configured for the **Master Instrument properties**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#syntax)

`Bars.Instrument.MasterInstrument.MergePolicy`

## [Property Value](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#property-value)

Represents the MergePolicy that is configured for the current master instrument.

Possible values are:

| Value | Description |
| --- | --- |
| **DoNotMerge** | No merge policy is applied |
| **MergeBackAdjusted** | Merge policy is applied between contracts along with rollover offsets |
| **MergeNonBackAdjusted** | Merge policy is applied between contracts without offsets |
| **UseGlobalSettings** | Uses the value configured from Tools -> Options -> Market Data |

## [Examples](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#examples)

```jsx-150469391 csharp
//Prints a warning, indicating what merge policy is in use if not using global settings**
if (Bars.Instrument.MasterInstrument.MergePolicy != MergePolicy.UseGlobalSettings)
{
 Print("Warning: Instrument has merge policy of " + Bars.Instrument.MasterInstrument.MergePolicy);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#definition)

Indicates the Merge Policy configured for the **Master Instrument properties**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#syntax)

`Bars.Instrument.MasterInstrument.MergePolicy`

## [Property Value](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#property-value)

Represents the MergePolicy that is configured for the current master instrument.

Possible values are:

| Value | Description |
| --- | --- |
| **DoNotMerge** | No merge policy is applied |
| **MergeBackAdjusted** | Merge policy is applied between contracts along with rollover offsets |
| **MergeNonBackAdjusted** | Merge policy is applied between contracts without offsets |
| **UseGlobalSettings** | Uses the value configured from Tools -> Options -> Market Data |

## [Examples](https://developer.ninjatrader.com/docs/desktop/mergepolicy\#examples)

```jsx-150469391 csharp
//Prints a warning, indicating what merge policy is in use if not using global settings**
if (Bars.Instrument.MasterInstrument.MergePolicy != MergePolicy.UseGlobalSettings)
{
 Print("Warning: Instrument has merge policy of " + Bars.Instrument.MasterInstrument.MergePolicy);
}

```