## [Definition](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#definition)

The number of seconds before the actual session end time that the **IsExitOnSessionCloseStrategy** function will trigger.

The time from which this property will be calculated is taken from the [Trading Hours](https://ninjatrader.com/support/helpguides/nt8/?trading_hours.htm) EOD property set in the strategy's Trading Hours template. The ExitOnSessionCloseSeconds property can either be set programmatically in the **OnStateChange()** method or be driven by the UI at run time.

## Note

This is a real-time only property, it will not have any effect on your ExitOnSessionClose time in backtesting processing historical data.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#property-value)

An int representing the number of seconds. Default value is 30.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#syntax)

`ExitOnSessionCloseSeconds`

## [Examples](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         // Triggers the exit on close function 30 seconds prior to trading day end
         IsExitOnSessionCloseStrategy = true;
         ExitOnSessionCloseSeconds = 30;
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#definition)

The number of seconds before the actual session end time that the **IsExitOnSessionCloseStrategy** function will trigger.

The time from which this property will be calculated is taken from the [Trading Hours](https://ninjatrader.com/support/helpguides/nt8/?trading_hours.htm) EOD property set in the strategy's Trading Hours template. The ExitOnSessionCloseSeconds property can either be set programmatically in the **OnStateChange()** method or be driven by the UI at run time.

## Note

This is a real-time only property, it will not have any effect on your ExitOnSessionClose time in backtesting processing historical data.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#property-value)

An int representing the number of seconds. Default value is 30.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#syntax)

`ExitOnSessionCloseSeconds`

## [Examples](https://developer.ninjatrader.com/docs/desktop/exitonsessioncloseseconds\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         // Triggers the exit on close function 30 seconds prior to trading day end
         IsExitOnSessionCloseStrategy = true;
         ExitOnSessionCloseSeconds = 30;
     }
}

```