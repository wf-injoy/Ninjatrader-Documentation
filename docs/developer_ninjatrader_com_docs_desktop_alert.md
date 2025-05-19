## [Definition](https://developer.ninjatrader.com/docs/desktop/alert\#definition)

Generates a visual/audible alert to display in the [Alerts Log](https://ninjatrader.com/support/helpguides/nt8/alerts_log.htm) window.

## Note

1. This method can only be called once the [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Realtime. Calls to this method in any other State will be silently ignored.
2. For add-ons, please see the [AlertCallback()](https://developer.ninjatrader.com/docs/desktop/alertcallback) method.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/alert\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/alert\#syntax)

`Alert(string id, Priority priority, string message, string soundLocation, int rearmSeconds, Brush backBrush, Brush foreColor)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/alert\#parameters)

| id | A string representing a unique id for the alert |
| priority | Sets the precedence of the alert in relation to other alerts. Possible values include: Priority.High, Priority.Low, Priority.Medium |
| message | A string representing the Alert message |
| soundLocation | A string representing the absolute file path of the .wav file to play |
| rearmSeconds | An int which sets the number of seconds an alert rearms. Note: If the same alert (identified by the id parameter) is called within a time window of the time of last alert + rearmSeconds, the alert will be ignored |
| backBrush | Sets the background color of the Alerts window row for this alert when triggered ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)) |
| foreBrush | Sets the foreground color of the Alerts window row for this alert when triggered ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)) |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using NinjaTrader.Core.Globals.InstallDir property. Please see the example below for usage.

## [Example](https://developer.ninjatrader.com/docs/desktop/alert\#example)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Generate an alert when the RSI value is greater or equal to 20
   if(RSI(14, 3)[0] >= 20)
     Alert("myAlert", Priority.High, "Reached threshold", NinjaTrader.Core.Globals.InstallDir+"\\sounds\\Alert1.wav", 10, Brushes.Black, Brushes.Yellow);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/alert\#definition)

Generates a visual/audible alert to display in the [Alerts Log](https://ninjatrader.com/support/helpguides/nt8/alerts_log.htm) window.

## Note

1. This method can only be called once the [State](https://developer.ninjatrader.com/docs/desktop/state) has reached State.Realtime. Calls to this method in any other State will be silently ignored.
2. For add-ons, please see the [AlertCallback()](https://developer.ninjatrader.com/docs/desktop/alertcallback) method.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/alert\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/alert\#syntax)

`Alert(string id, Priority priority, string message, string soundLocation, int rearmSeconds, Brush backBrush, Brush foreColor)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/alert\#parameters)

| id | A string representing a unique id for the alert |
| priority | Sets the precedence of the alert in relation to other alerts. Possible values include: Priority.High, Priority.Low, Priority.Medium |
| message | A string representing the Alert message |
| soundLocation | A string representing the absolute file path of the .wav file to play |
| rearmSeconds | An int which sets the number of seconds an alert rearms. Note: If the same alert (identified by the id parameter) is called within a time window of the time of last alert + rearmSeconds, the alert will be ignored |
| backBrush | Sets the background color of the Alerts window row for this alert when triggered ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)) |
| foreBrush | Sets the foreground color of the Alerts window row for this alert when triggered ( [reference](http://msdn.microsoft.com/en-us/library/system.drawing.color_members(v=vs.90).aspx)) |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using NinjaTrader.Core.Globals.InstallDir property. Please see the example below for usage.

## [Example](https://developer.ninjatrader.com/docs/desktop/alert\#example)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Generate an alert when the RSI value is greater or equal to 20
   if(RSI(14, 3)[0] >= 20)
     Alert("myAlert", Priority.High, "Reached threshold", NinjaTrader.Core.Globals.InstallDir+"\\sounds\\Alert1.wav", 10, Brushes.Black, Brushes.Yellow);
}

```