## [Definition](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#definition)

Provides a way to use your own custom events (such as a Timer object) so that internal NinjaScript indexes and pointers are correctly set prior to processing user code triggered by your custom event. When calling this event, NinjaTrader will synchronize all internal pointers and then call your custom event handler where your user code is located.

## Note

The TriggerCustomEvent() method does NOT execute before State.DataLoaded or during or after State.Terminated.  In effect, attempting to trigger custom events may be unavailable in some circumstances (e.g., while an indicator is terminating, or viewing the [Strategy Analyzer](https://ninjatrader.com/support/helpGuides/nt8/?strategy_analyzer.htm) chart display after backtest has completed, etc.)

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#method-return-value)

This method does not have a return value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#syntax)

`TriggerCustomEvent(Action<` object `> customEvent, object state)`

`TriggerCustomEvent(Action<` object `> customEvent, int barsSeriesIndex, object state)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#parameters)

| Parameter | Description |
| --- | --- |
| barsIndex | Index of the [bar series](https://developer.ninjatrader.com/docs/desktop/barsinprogress) you want to synchronize to |
| customEvent | [Delegate](http://msdn.microsoft.com/en-us/library/018hxwa8%28v=vs.110%29.aspx) of your custom event method |
| state | Any object you want passed into your custom event method |

## Note

Tips:

- There may be scenarios in which you need to set a [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest) value outside of one of the core data event methods.  In these cases, you can use TriggerCustomEvent() to reliably synchronize the barAgo indexer to the recent.  current bar being updated.  Please see the example below.
- Usually the correct approach is to use the WPF Dispatcher timer, however in cases where you need the timer to update a WinForms window it opened - please use the [WinForms timer](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.timer?view=netframework-4.7.2).

## [Examples](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#examples)

### Using TriggerCustomEvent() in simple timer event

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // OnBarUpdate() only runs as bars are processed, which is not guaranteed to occur at a specific interval
    // e.g., even on a 5 second bar series, there may be time periods where there are no updates due to low trading activity
    // or could be buffered due to running Calculate.OnBarClose. Instead of trying to obtain the Close[0] value
    // at some interval here, we are going to do it in our custom TimerEventProcessor
}

// This is the method to run when the timer is raised.
private void TimerEventProcessor(Object myObject, EventArgs myEventArgs)
{
    // Do not process your code here but instead call the TriggerCustomEvent() method
    // and process your code in the custom handler method e.g., our custom PrintThePrice()
    // Doing so ensures all internal indexers are up-to-date
    if (CurrentBar > 0)
    {
      TriggerCustomEvent(PrintThePrice, Close[0]);
    }
}

// Print the latest closing price with the current time
private void PrintThePrice(object price)
{
    Print("The Last Bar's Closing Value as of " + NinjaTrader.Core.Globals.Now + " was " + price);
}

// Declare the WPF dispatcher timer
private System.Timers.Timer myTimer;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
      Name = "SampleTriggerCustomEventTimer";
    }
    else if (State == State.DataLoaded)
    {
        // Instantiates the timer and sets the interval to 5 seconds.
        myTimer = new System.Timers.Timer(5000);
        // Adds the event handler for the method that will
        // process the timer event to the timer.
        myTimer.Elapsed += TimerEventProcessor;
        // Starts the timer
        myTimer.Enabled = true;
    }
    else if (State == State.Terminated)
    {
        // Stops the timer and removes the timer event handler
        if (myTimer != null)
        {
            myTimer.Enabled = false;
            myTimer.Elapsed -= TimerEventProcessor;
            myTimer = null;
        }
    }
}

```

### Using TriggerCustomEvent to update a previously set custom Series< `T` \> value

```jsx-150469391 csharp
// using the virtual on render method for demonstration
// but concept could apply to any custom event that does not rely on bars data
// e.g., from a custom mouse event or other 3rd party dependency
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // we want to reset a custom series values 20 barsAgo during some condition
  if (conditionWhichRequiredUpdate)
  {
    // First, synchronize the index value used in via Series[barsAgo]
    // to the NinjaScriptBase.CurrentBar being currently being processed in OnBarUpdate
    TriggerCustomEvent(o =>
    {
        // For debugging, check the previous value
        Print("Before value which was set in OnBarUpdate(): " + SomeVolumeData[20]);

        SomeVolumeData[20] = 5; // set to our new custom value

        // For debugging, check the updated value
        Print("After value which was updated later in OnRender(): " + SomeVolumeData[20]);
    }, null);

    // reset our flag until we need to update a value again
    conditionWhichRequiredUpdate = false;
  }
  //Output:
  //Before value which was set in OnBarUpdate(): 1165
  //After value which was updated later in OnRender(): 5
}

private Series<double> SomeVolumeData; // custom Series for tracking volume which will be modified through its lifetime
private bool conditionWhichRequiredUpdate = true;

protected override void OnStateChange()
{
  protected override void OnStateChange()
  {
    if (State == State.SetDefaults)
    {
        Name = "SampleUpdateCustomSeries";
    }

    else if (State == State.Historical)
    {
        SomeVolumeData = new Series<double>(this);
    }
  }
}

protected override void OnBarUpdate()
{
  SomeVolumeData[0] = Volume[0]; // set the custom series to the CurrentBar volume
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#definition)

Provides a way to use your own custom events (such as a Timer object) so that internal NinjaScript indexes and pointers are correctly set prior to processing user code triggered by your custom event. When calling this event, NinjaTrader will synchronize all internal pointers and then call your custom event handler where your user code is located.

## Note

The TriggerCustomEvent() method does NOT execute before State.DataLoaded or during or after State.Terminated.  In effect, attempting to trigger custom events may be unavailable in some circumstances (e.g., while an indicator is terminating, or viewing the [Strategy Analyzer](https://ninjatrader.com/support/helpGuides/nt8/?strategy_analyzer.htm) chart display after backtest has completed, etc.)

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#method-return-value)

This method does not have a return value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#syntax)

`TriggerCustomEvent(Action<` object `> customEvent, object state)`

`TriggerCustomEvent(Action<` object `> customEvent, int barsSeriesIndex, object state)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#parameters)

| Parameter | Description |
| --- | --- |
| barsIndex | Index of the [bar series](https://developer.ninjatrader.com/docs/desktop/barsinprogress) you want to synchronize to |
| customEvent | [Delegate](http://msdn.microsoft.com/en-us/library/018hxwa8%28v=vs.110%29.aspx) of your custom event method |
| state | Any object you want passed into your custom event method |

## Note

Tips:

- There may be scenarios in which you need to set a [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest) value outside of one of the core data event methods.  In these cases, you can use TriggerCustomEvent() to reliably synchronize the barAgo indexer to the recent.  current bar being updated.  Please see the example below.
- Usually the correct approach is to use the WPF Dispatcher timer, however in cases where you need the timer to update a WinForms window it opened - please use the [WinForms timer](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.timer?view=netframework-4.7.2).

## [Examples](https://developer.ninjatrader.com/docs/desktop/triggercustomevent\#examples)

### Using TriggerCustomEvent() in simple timer event

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // OnBarUpdate() only runs as bars are processed, which is not guaranteed to occur at a specific interval
    // e.g., even on a 5 second bar series, there may be time periods where there are no updates due to low trading activity
    // or could be buffered due to running Calculate.OnBarClose. Instead of trying to obtain the Close[0] value
    // at some interval here, we are going to do it in our custom TimerEventProcessor
}

// This is the method to run when the timer is raised.
private void TimerEventProcessor(Object myObject, EventArgs myEventArgs)
{
    // Do not process your code here but instead call the TriggerCustomEvent() method
    // and process your code in the custom handler method e.g., our custom PrintThePrice()
    // Doing so ensures all internal indexers are up-to-date
    if (CurrentBar > 0)
    {
      TriggerCustomEvent(PrintThePrice, Close[0]);
    }
}

// Print the latest closing price with the current time
private void PrintThePrice(object price)
{
    Print("The Last Bar's Closing Value as of " + NinjaTrader.Core.Globals.Now + " was " + price);
}

// Declare the WPF dispatcher timer
private System.Timers.Timer myTimer;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
      Name = "SampleTriggerCustomEventTimer";
    }
    else if (State == State.DataLoaded)
    {
        // Instantiates the timer and sets the interval to 5 seconds.
        myTimer = new System.Timers.Timer(5000);
        // Adds the event handler for the method that will
        // process the timer event to the timer.
        myTimer.Elapsed += TimerEventProcessor;
        // Starts the timer
        myTimer.Enabled = true;
    }
    else if (State == State.Terminated)
    {
        // Stops the timer and removes the timer event handler
        if (myTimer != null)
        {
            myTimer.Enabled = false;
            myTimer.Elapsed -= TimerEventProcessor;
            myTimer = null;
        }
    }
}

```

### Using TriggerCustomEvent to update a previously set custom Series< `T` \> value

```jsx-150469391 csharp
// using the virtual on render method for demonstration
// but concept could apply to any custom event that does not rely on bars data
// e.g., from a custom mouse event or other 3rd party dependency
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
  // we want to reset a custom series values 20 barsAgo during some condition
  if (conditionWhichRequiredUpdate)
  {
    // First, synchronize the index value used in via Series[barsAgo]
    // to the NinjaScriptBase.CurrentBar being currently being processed in OnBarUpdate
    TriggerCustomEvent(o =>
    {
        // For debugging, check the previous value
        Print("Before value which was set in OnBarUpdate(): " + SomeVolumeData[20]);

        SomeVolumeData[20] = 5; // set to our new custom value

        // For debugging, check the updated value
        Print("After value which was updated later in OnRender(): " + SomeVolumeData[20]);
    }, null);

    // reset our flag until we need to update a value again
    conditionWhichRequiredUpdate = false;
  }
  //Output:
  //Before value which was set in OnBarUpdate(): 1165
  //After value which was updated later in OnRender(): 5
}

private Series<double> SomeVolumeData; // custom Series for tracking volume which will be modified through its lifetime
private bool conditionWhichRequiredUpdate = true;

protected override void OnStateChange()
{
  protected override void OnStateChange()
  {
    if (State == State.SetDefaults)
    {
        Name = "SampleUpdateCustomSeries";
    }

    else if (State == State.Historical)
    {
        SomeVolumeData = new Series<double>(this);
    }
  }
}

protected override void OnBarUpdate()
{
  SomeVolumeData[0] = Volume[0]; // set the custom series to the CurrentBar volume
}

```