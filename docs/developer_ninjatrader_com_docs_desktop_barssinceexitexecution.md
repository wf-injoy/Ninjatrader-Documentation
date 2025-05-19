## [Definition](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#definition)

Returns the number of bars that have elapsed since the last exit. When a signal name is provided, the number of bars that have elapsed since that last specific exit will be returned.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#method-return-value)

An **int** value that represents a number of bars. A value of -1 will be returned if a previous exit does not exist.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#syntax)

`BarsSinceExitExecution()`

`BarsSinceExitExecution(string signalName)`

The following method signature should be used when working with [multi-time frame and instrument strategies](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments):

BarsSinceExitExecution(int barsInProgressIndex, string signalName, int exitExecutionsAgo)

## Note

When working with a multi-series strategy the BarsSinceExitExecution() will return you the elapsed bars as determined by the first Bars object for the instrument specified in the barsInProgressIndex.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#parameters)

| signalName | The signal name of an exit order specified in an order exit method. |
| barsInProgressIndex | The index of the Bars object the entry order was submitted against. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |
| exitExecutionsAgo | Number of exit executions ago. Pass in 0 for the number of bars since the last exit execution. |

## Note

Please see [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss), [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) or [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) for their corresponding signal name

## [Examples](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (CurrentBar < BarsRequiredToTrade)
       return;

   // Only enter if at least 10 bars has passed since our last exit or if we have never traded yet
   if ((BarsSinceExitExecution() > 10 || BarsSinceExitExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
       EnterLong();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#definition)

Returns the number of bars that have elapsed since the last exit. When a signal name is provided, the number of bars that have elapsed since that last specific exit will be returned.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#method-return-value)

An **int** value that represents a number of bars. A value of -1 will be returned if a previous exit does not exist.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#syntax)

`BarsSinceExitExecution()`

`BarsSinceExitExecution(string signalName)`

The following method signature should be used when working with [multi-time frame and instrument strategies](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments):

BarsSinceExitExecution(int barsInProgressIndex, string signalName, int exitExecutionsAgo)

## Note

When working with a multi-series strategy the BarsSinceExitExecution() will return you the elapsed bars as determined by the first Bars object for the instrument specified in the barsInProgressIndex.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#parameters)

| signalName | The signal name of an exit order specified in an order exit method. |
| barsInProgressIndex | The index of the Bars object the entry order was submitted against. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |
| exitExecutionsAgo | Number of exit executions ago. Pass in 0 for the number of bars since the last exit execution. |

## Note

Please see [SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss), [SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget) or [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) for their corresponding signal name

## [Examples](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (CurrentBar < BarsRequiredToTrade)
       return;

   // Only enter if at least 10 bars has passed since our last exit or if we have never traded yet
   if ((BarsSinceExitExecution() > 10 || BarsSinceExitExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
       EnterLong();
}

```