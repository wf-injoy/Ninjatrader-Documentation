## [Definition](https://developer.ninjatrader.com/docs/desktop/onstatechange\#definition)

An event driven method which is called whenever the script enters a new **State**. The **OnStateChange()** method can be used to configure script properties, create one-time behavior when going from historical to real-time, as well as manage clean up resources on termination.

## Note

Notes:

- Viewing any UI element which lists NinjaScript classes (such as the Indicators or Strategies window, a chart's Chart Style dropdown menu, etc.) will initialize all classes of that Type when it is opened, which causes each script to enter **State.SetDefaults**, even if it is not actively configured or running in any window. It is important to keep this in mind when adding logic within **State.SetDefaults** in **OnStateChange()**, as this logic will be processed each time the script is initialized. For example, opening the Indicators window will trigger **State.SetDefaults** for all indicators in the system, and closing the Indicators window will trigger **State.Terminated** for all Indicators. In addition, disconnecting or connecting to a data provider can cause State transitions for any currently active scripts. Further discussion of this aspect of the state change model can be found via [Understanding the lifecycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of).
- When an indicator is configured on a chart while a Compile is taking place in the NinjaScript Editor, it can appear that the script passes through **State.Terminated**. However, this is the result of a copy of the script being initialized at compile-time, NOT the result of the indicator on the chart being disabled and re-initialized.

## [Related Methods and Properties](https://developer.ninjatrader.com/docs/desktop/onstatechange\#related-methods-and-properties)

| [SetState()](https://developer.ninjatrader.com/docs/desktop/setstate) | Method is used for changing the State of any running NinjaScript object. |
| [State](https://developer.ninjatrader.com/docs/desktop/state) | Represents the current progression of the object as it advances from setup, processing data, to termination. |

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onstatechange\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onstatechange\#syntax)

See example below. The NinjaScript wizards automatically generate the method syntax for you.

Possible states are:

| State Name | This state is called when | This state is where you should |
| --- | --- | --- |
| **State.SetDefaults** | SetDefaults is always called when displaying objects in a UI list such as the Indicators dialogue window since temporary objects are created for the purpose of UI display | - Keep as lean as possible \* Set default values (pushed to UI) |
| **State.Configure** | Configure is called after a user adds an object to the applied list of objects and presses the OK or Apply button. This state is called only once for the life of the object. | - Add additional data series via [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) _Declare custom resources_ Override and configure values set by the UI |
| **State.Active** | Active is called once after the object is configured and is ready to process data (DrawingTools could see multiple calls as internally an object for hit testing is cloned) | - Used for objects such as [Share Service](https://developer.ninjatrader.com/docs/desktop/share_service) which do not process price series data \* Indicate the object is ready to being processing information |
| **State.DataLoaded** | DataLoaded is called only once after all data series have been loaded. | - Use for logic that needs to access data related objects like Bars, Instruments, BarsPeriod, TradingHours or instantiating indicators _Notify that all data series have been loaded_ Initialize any class level variables (including custom [Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) objects) |
| **State.Historical** | Historical is called once the object begins to process historical data. This state is called once when running an object in real-time. This object is called multiple times when running a backtest optimization and the property [IsInstantiatedOnEachOptimizationIteration](https://developer.ninjatrader.com/docs/desktop/isinstantiatedoneachoptimizationiteration) is true (default behavior) | - Notify that the object is processing historical data |
| **State.Transition** | Transition is called once as the object has finished processing historical data but before it starts to process realtime data. | - Notify that the indicator or strategy is transitioning to realtime data \* Prepare realtime related resources |
| **State.Realtime** | Realtime is called once when the object begins to process realtime data. | - Notify that the indicator or strategy is processing realtime data \* Execute realtime related logic |
| **State.Terminated** | Terminated is called once when the object terminates. | - Notify the object is shutting down \* Use to clean up/dispose of resources |

## [Active States vs Data Processing States](https://developer.ninjatrader.com/docs/desktop/onstatechange\#active-states-vs-data-processing-states)

After **State.Configure**, each type of NinjaScript type has its own state management system which can be classified under two categories:

- Active state: **State.Active**

- Data Processing states: **State.DataLoaded**, **State.Historical**, **State.Transition**, **State.Realtime**


The table below lists each NinjaScript type and its designed state management system:

| NinjaScript Type | State Management System |
| --- | --- |
| AddOns\* | Active state |
| BarTypes | Active state |
| ChartStyles | Active state |
| DrawingTools | Active state |
| Indicators | Data Processing states |
| ImportTypes | Active state |
| Market Analyzer Columns | Data Processing states |
| OptimizationFitnesses | Active state |
| Optimizers | Active state |
| PerformanceMetrics | Active state |
| ShareServices | Active state |
| Strategies | Data Processing states |
| SuperDOM Columns | Active state |

## Note

Tips:

- Resources created in **State.Configure** and not disposed of immediately will be kept and utilized if the NinjaScript object resides in grids (e.g. Strategy tab on Control Center), even if it is not enabled. Try to create resources in **State.Historical** or **State.DataLoaded** instead, if possible.
- **State.Historical** is called multiple times when running a backtest [optimization](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?optimize_a_strategy.htm) on a strategy and the property " [IsInstantiatedOnEachOptimizationIteration](https://developer.ninjatrader.com/docs/desktop/isinstantiatedoneachoptimizationiteration)" is true (default behavior).
- Embedded scripts within a calling parent script should not use a different Calculate property since it is already utilizing the Calculate property of the parent script (i.e. the strategy your indicator is called from).
- Since the parent NinjaScript therefore governs this setting, it should be set to the highest needed setting satisfying all its children.
- When instantiating indicators in a [Multi-Series script](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) in **OnStateChange**, the input any hosted indicator is running on should be explicitly stated (since a specific [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) is not guaranteed)

## [Examples](https://developer.ninjatrader.com/docs/desktop/onstatechange\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Calculate once at the end of every single bar
        Calculate = Calculate.OnBarClose;

        // Add two plots
        AddPlot(Brushes.Blue, "Upper");
        AddPlot(Brushes.Orange, "Lower");
    }
    else if (State == State.Configure)
    {
        // Adds a 5-minute Bars object to the strategy and is automatically assigned
        // a Bars object index of 1 since the primary data the strategy is run against
        // set by the UI takes the index of 0.
        AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onstatechange\#definition)

An event driven method which is called whenever the script enters a new **State**. The **OnStateChange()** method can be used to configure script properties, create one-time behavior when going from historical to real-time, as well as manage clean up resources on termination.

## Note

Notes:

- Viewing any UI element which lists NinjaScript classes (such as the Indicators or Strategies window, a chart's Chart Style dropdown menu, etc.) will initialize all classes of that Type when it is opened, which causes each script to enter **State.SetDefaults**, even if it is not actively configured or running in any window. It is important to keep this in mind when adding logic within **State.SetDefaults** in **OnStateChange()**, as this logic will be processed each time the script is initialized. For example, opening the Indicators window will trigger **State.SetDefaults** for all indicators in the system, and closing the Indicators window will trigger **State.Terminated** for all Indicators. In addition, disconnecting or connecting to a data provider can cause State transitions for any currently active scripts. Further discussion of this aspect of the state change model can be found via [Understanding the lifecycle of your NinjaScript objects](https://developer.ninjatrader.com/docs/desktop/understanding_the_lifecycle_of).
- When an indicator is configured on a chart while a Compile is taking place in the NinjaScript Editor, it can appear that the script passes through **State.Terminated**. However, this is the result of a copy of the script being initialized at compile-time, NOT the result of the indicator on the chart being disabled and re-initialized.

## [Related Methods and Properties](https://developer.ninjatrader.com/docs/desktop/onstatechange\#related-methods-and-properties)

| [SetState()](https://developer.ninjatrader.com/docs/desktop/setstate) | Method is used for changing the State of any running NinjaScript object. |
| [State](https://developer.ninjatrader.com/docs/desktop/state) | Represents the current progression of the object as it advances from setup, processing data, to termination. |

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onstatechange\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onstatechange\#syntax)

See example below. The NinjaScript wizards automatically generate the method syntax for you.

Possible states are:

| State Name | This state is called when | This state is where you should |
| --- | --- | --- |
| **State.SetDefaults** | SetDefaults is always called when displaying objects in a UI list such as the Indicators dialogue window since temporary objects are created for the purpose of UI display | - Keep as lean as possible \* Set default values (pushed to UI) |
| **State.Configure** | Configure is called after a user adds an object to the applied list of objects and presses the OK or Apply button. This state is called only once for the life of the object. | - Add additional data series via [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) _Declare custom resources_ Override and configure values set by the UI |
| **State.Active** | Active is called once after the object is configured and is ready to process data (DrawingTools could see multiple calls as internally an object for hit testing is cloned) | - Used for objects such as [Share Service](https://developer.ninjatrader.com/docs/desktop/share_service) which do not process price series data \* Indicate the object is ready to being processing information |
| **State.DataLoaded** | DataLoaded is called only once after all data series have been loaded. | - Use for logic that needs to access data related objects like Bars, Instruments, BarsPeriod, TradingHours or instantiating indicators _Notify that all data series have been loaded_ Initialize any class level variables (including custom [Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) objects) |
| **State.Historical** | Historical is called once the object begins to process historical data. This state is called once when running an object in real-time. This object is called multiple times when running a backtest optimization and the property [IsInstantiatedOnEachOptimizationIteration](https://developer.ninjatrader.com/docs/desktop/isinstantiatedoneachoptimizationiteration) is true (default behavior) | - Notify that the object is processing historical data |
| **State.Transition** | Transition is called once as the object has finished processing historical data but before it starts to process realtime data. | - Notify that the indicator or strategy is transitioning to realtime data \* Prepare realtime related resources |
| **State.Realtime** | Realtime is called once when the object begins to process realtime data. | - Notify that the indicator or strategy is processing realtime data \* Execute realtime related logic |
| **State.Terminated** | Terminated is called once when the object terminates. | - Notify the object is shutting down \* Use to clean up/dispose of resources |

## [Active States vs Data Processing States](https://developer.ninjatrader.com/docs/desktop/onstatechange\#active-states-vs-data-processing-states)

After **State.Configure**, each type of NinjaScript type has its own state management system which can be classified under two categories:

- Active state: **State.Active**

- Data Processing states: **State.DataLoaded**, **State.Historical**, **State.Transition**, **State.Realtime**


The table below lists each NinjaScript type and its designed state management system:

| NinjaScript Type | State Management System |
| --- | --- |
| AddOns\* | Active state |
| BarTypes | Active state |
| ChartStyles | Active state |
| DrawingTools | Active state |
| Indicators | Data Processing states |
| ImportTypes | Active state |
| Market Analyzer Columns | Data Processing states |
| OptimizationFitnesses | Active state |
| Optimizers | Active state |
| PerformanceMetrics | Active state |
| ShareServices | Active state |
| Strategies | Data Processing states |
| SuperDOM Columns | Active state |

## Note

Tips:

- Resources created in **State.Configure** and not disposed of immediately will be kept and utilized if the NinjaScript object resides in grids (e.g. Strategy tab on Control Center), even if it is not enabled. Try to create resources in **State.Historical** or **State.DataLoaded** instead, if possible.
- **State.Historical** is called multiple times when running a backtest [optimization](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?optimize_a_strategy.htm) on a strategy and the property " [IsInstantiatedOnEachOptimizationIteration](https://developer.ninjatrader.com/docs/desktop/isinstantiatedoneachoptimizationiteration)" is true (default behavior).
- Embedded scripts within a calling parent script should not use a different Calculate property since it is already utilizing the Calculate property of the parent script (i.e. the strategy your indicator is called from).
- Since the parent NinjaScript therefore governs this setting, it should be set to the highest needed setting satisfying all its children.
- When instantiating indicators in a [Multi-Series script](https://developer.ninjatrader.com/docs/desktop/multi_time_frame_instruments) in **OnStateChange**, the input any hosted indicator is running on should be explicitly stated (since a specific [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) is not guaranteed)

## [Examples](https://developer.ninjatrader.com/docs/desktop/onstatechange\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Calculate once at the end of every single bar
        Calculate = Calculate.OnBarClose;

        // Add two plots
        AddPlot(Brushes.Blue, "Upper");
        AddPlot(Brushes.Orange, "Lower");
    }
    else if (State == State.Configure)
    {
        // Adds a 5-minute Bars object to the strategy and is automatically assigned
        // a Bars object index of 1 since the primary data the strategy is run against
        // set by the UI takes the index of 0.
        AddDataSeries("AAPL", BarsPeriodType.Minute, 5);
    }
}

```