## [Definition](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#definition)

Returns the current futures expiry compared to the time of the input value used for the method.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#method-return-value)

A **DateTime** structure

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#syntax)

`Bars.Instrument.MasterInstrument.GetNextExpiry(DateTime afterDate)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#parameters)

| **afterDate** | A **DateTime** value representing to be compared |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#examples)

```jsx-150469391 csharp
// Indicates what the current expiry is in the bottom right of the chart
Draw.TextFixed(this, "tag1", "The current expiry is " + Bars.Instrument.MasterInstrument.GetNextExpiry(DateTime.Now).ToString("MM-yy"), TextPosition.BottomRight);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#definition)

Returns the current futures expiry compared to the time of the input value used for the method.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#method-return-value)

A **DateTime** structure

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#syntax)

`Bars.Instrument.MasterInstrument.GetNextExpiry(DateTime afterDate)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#parameters)

| **afterDate** | A **DateTime** value representing to be compared |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getnextexpiry\#examples)

```jsx-150469391 csharp
// Indicates what the current expiry is in the bottom right of the chart
Draw.TextFixed(this, "tag1", "The current expiry is " + Bars.Instrument.MasterInstrument.GetNextExpiry(DateTime.Now).ToString("MM-yy"), TextPosition.BottomRight);

```