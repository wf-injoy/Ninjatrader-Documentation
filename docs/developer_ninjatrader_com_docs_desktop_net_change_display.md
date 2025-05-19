## [Description](https://developer.ninjatrader.com/docs/desktop/net_change_display\#description)

Displays net change on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/net_change_display\#syntax)

`NetChangeDisplay(PerformanceUnit, NetChangePosition location)`

`NetChangeDisplay(ISeries<double> input, PerformanceUnit, NetChangePosition location)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/net_change_display\#return-value)

double

## [Parameters](https://developer.ninjatrader.com/docs/desktop/net_change_display\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **PerformanceUnit** | Format of the calculation of net change |
| **NetChangePosition** | Location to display net change on the chart |

## [Examples](https://developer.ninjatrader.com/docs/desktop/net_change_display\#examples)

```jsx-150469391 csharp

// Runs on realtime since there is no historical data for this indicator
if (State == State.Historical)
	return;
else if (State >= State.Realtime)
{
	// Prints the current tick value of the net change
	var ncd = NetChangeDisplay(PerformanceUnit.Ticks, NetChangePosition.BottomRight);
	Print("The current Net Change value is " + ncd.NetChange);
}

```

## Note

This indicator only plots real-time. Historical values will print as 0.

## [Description](https://developer.ninjatrader.com/docs/desktop/net_change_display\#description)

Displays net change on the chart.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/net_change_display\#syntax)

`NetChangeDisplay(PerformanceUnit, NetChangePosition location)`

`NetChangeDisplay(ISeries<double> input, PerformanceUnit, NetChangePosition location)`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/net_change_display\#return-value)

double

## [Parameters](https://developer.ninjatrader.com/docs/desktop/net_change_display\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **PerformanceUnit** | Format of the calculation of net change |
| **NetChangePosition** | Location to display net change on the chart |

## [Examples](https://developer.ninjatrader.com/docs/desktop/net_change_display\#examples)

```jsx-150469391 csharp

// Runs on realtime since there is no historical data for this indicator
if (State == State.Historical)
	return;
else if (State >= State.Realtime)
{
	// Prints the current tick value of the net change
	var ncd = NetChangeDisplay(PerformanceUnit.Ticks, NetChangePosition.BottomRight);
	Print("The current Net Change value is " + ncd.NetChange);
}

```

## Note

This indicator only plots real-time. Historical values will print as 0.