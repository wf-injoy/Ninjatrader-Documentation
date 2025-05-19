## [Definition](https://developer.ninjatrader.com/docs/desktop/alertcallback\#definition)

Creates an alert event to be raised specified by a string "id" and a corresponding .wav file will be played matching the "soundLocation" parameter. Once an alert has triggered, its message is reflected in the "Alerts Log" window based on the background and foreground brushes provided in the callback.

## Note

1. If the AlertCallback() method is called again with the same string "id" parameter before the provided "rearmSeconds" duration has passed, the alert event will be reset based on the new "rearmSeconds" parameter provided. Doing so could consequently cause an alert to be reset inadvertently, in which case you should pass a "rearmSeconds" parameter of "0" to ensure the specified alert event is always raised.
2. The AlertCallback() method is the same core function used by the simpler [Alert()](https://developer.ninjatrader.com/docs/desktop/alert) method which can alternatively be used with NinjaScript indicators and strategies. The AlertCallback() was exposed for use with Add-ons or other more advance use cases.
3. Providing a "rearmSeconds" parameter greater than "0" will add the matching alert id to a rearmed state, which only allows the alert to be reissued after the specified time interval in seconds has lapsed. You can reset an alert's rearm parameter by using the [ResetAlertRearmById()](https://developer.ninjatrader.com/docs/desktop/rearmalert).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/alertcallback\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/alertcallback\#syntax)

`NinjaTrader.NinjaScript.Alert.AlertCallback(Instrument instrument, object source, string id, DateTime time, Priority priority, string message, string soundLocation, Brush backBrush, Brush foreBrush, int rearmSeconds)`

## Warning

An "id" parameter MUST be provided otherwise a null argument exception will be generated

## [Parameters](https://developer.ninjatrader.com/docs/desktop/alertcallback\#parameters)

| instrument | An [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) object associated with the alert. |
| source | A generic object type which created the alert (e.g. "this") |
| id | A string representing a unique id for the alert |
| time | The DateTime representing the time associated with the alert |
| priority | Sets the precedence of the alert in relation to other alerts. Any one of the following values: Priority.High, Priority.Low, Priority.Medium |
| message | A string representing the Alert message |
| soundLocation | A string representing the absolute file path of the .wav file to play. |
| backBrush | Sets the background color of the Alerts window row for this alert when triggered |
| foreBrush | Sets the foreground color of the Alerts window row for this alert when triggered |
| rearmSeconds | An int which sets the number of seconds an alert will rearm. Note: If the same alert (identified by the id parameter) is called within a time window of the time of last alert + rearmSeconds, the alert will be ignored. |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using NinjaTrader.Core.Globals.InstallDir property. Please see the example below for usage.

## [Examples](https://developer.ninjatrader.com/docs/desktop/alertcallback\#examples)

```jsx-1168641291 csharp
NinjaTrader.NinjaScript.Alert.AlertCallback(NinjaTrader.Cbi.Instrument.GetInstrument("MSFT"), this, "someId", NinjaTrader.Core.Globals.Now, Priority.High, "message", NinjaTrader.Core.Globals.InstallDir+@"\sounds\Alert1.wav", new SolidColorBrush(Colors.Blue), new SolidColorBrush(Colors.White), 0);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/alertcallback\#definition)

Creates an alert event to be raised specified by a string "id" and a corresponding .wav file will be played matching the "soundLocation" parameter. Once an alert has triggered, its message is reflected in the "Alerts Log" window based on the background and foreground brushes provided in the callback.

## Note

1. If the AlertCallback() method is called again with the same string "id" parameter before the provided "rearmSeconds" duration has passed, the alert event will be reset based on the new "rearmSeconds" parameter provided. Doing so could consequently cause an alert to be reset inadvertently, in which case you should pass a "rearmSeconds" parameter of "0" to ensure the specified alert event is always raised.
2. The AlertCallback() method is the same core function used by the simpler [Alert()](https://developer.ninjatrader.com/docs/desktop/alert) method which can alternatively be used with NinjaScript indicators and strategies. The AlertCallback() was exposed for use with Add-ons or other more advance use cases.
3. Providing a "rearmSeconds" parameter greater than "0" will add the matching alert id to a rearmed state, which only allows the alert to be reissued after the specified time interval in seconds has lapsed. You can reset an alert's rearm parameter by using the [ResetAlertRearmById()](https://developer.ninjatrader.com/docs/desktop/rearmalert).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/alertcallback\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/alertcallback\#syntax)

`NinjaTrader.NinjaScript.Alert.AlertCallback(Instrument instrument, object source, string id, DateTime time, Priority priority, string message, string soundLocation, Brush backBrush, Brush foreBrush, int rearmSeconds)`

## Warning

An "id" parameter MUST be provided otherwise a null argument exception will be generated

## [Parameters](https://developer.ninjatrader.com/docs/desktop/alertcallback\#parameters)

| instrument | An [Instrument](https://developer.ninjatrader.com/docs/desktop/instrument) object associated with the alert. |
| source | A generic object type which created the alert (e.g. "this") |
| id | A string representing a unique id for the alert |
| time | The DateTime representing the time associated with the alert |
| priority | Sets the precedence of the alert in relation to other alerts. Any one of the following values: Priority.High, Priority.Low, Priority.Medium |
| message | A string representing the Alert message |
| soundLocation | A string representing the absolute file path of the .wav file to play. |
| backBrush | Sets the background color of the Alerts window row for this alert when triggered |
| foreBrush | Sets the foreground color of the Alerts window row for this alert when triggered |
| rearmSeconds | An int which sets the number of seconds an alert will rearm. Note: If the same alert (identified by the id parameter) is called within a time window of the time of last alert + rearmSeconds, the alert will be ignored. |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using NinjaTrader.Core.Globals.InstallDir property. Please see the example below for usage.

## [Examples](https://developer.ninjatrader.com/docs/desktop/alertcallback\#examples)

```jsx-1168641291 csharp
NinjaTrader.NinjaScript.Alert.AlertCallback(NinjaTrader.Cbi.Instrument.GetInstrument("MSFT"), this, "someId", NinjaTrader.Core.Globals.Now, Priority.High, "message", NinjaTrader.Core.Globals.InstallDir+@"\sounds\Alert1.wav", new SolidColorBrush(Colors.Blue), new SolidColorBrush(Colors.White), 0);

```