## [Description](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#description)

An indicator that accumulates the volume of orders filled at bid and ask prices or up and down ticks throughout the session and compares them to determine buy/sell pressure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#syntax)

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter)`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter)`

**Returns Open value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaOpen[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaOpen[int barsAgo]`

**Returns High value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaHigh[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaHigh[int barsAgo]`

**Returns Low value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaLow[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaLow[int barsAgo]`

**Returns Close value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaClose[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaClose[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| deltaType | The type of data to delta calculates on:<br>- BidAsk<br>- UpDownTick |
| period | The period in which the delta accumulates:<br>- Session<br>- Bar |
| sizeFilter | Input to exclude volume less than the selected value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#examples)

```jsx-150469391 csharp
// Calling the OrderFlowCumulativeDelta() method directly
// A 1 tick data series must be added to the OnStateChange() as this indicator runs off of tick data
else if (State == State.Configure)
{
   AddDataSeries(Data.BarsPeriodType.Tick, 1);
}

// OnBarUpdate() logic
if (BarsInProgress == 0)
{
    // Print the close of the cumulative delta bar with a delta type of Bid Ask and with a Session period
    Print("Delta Close: " + OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).DeltaClose[0]);
}
else if (BarsInProgress == 1)
{
    // We have to update the secondary series of the cached indicator to make sure the values we get in BarsInProgress == 0 are in sync
    OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).Update(OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).BarsArray[1].Count - 1, 1);
}

```

```jsx-150469391 csharp
// Calling the OrderFlowCumulativeDelta() method by reference

// A 1 tick data series must be added to OnStateChange() as this indicator runs off of tick data
else if (State == State.Configure)
{
    AddDataSeries(Data.BarsPeriodType.Tick, 1);
}
else if (State == State.DataLoaded)
{
    // Instantiate the indicator
    cumulativeDelta = OrderFlowCumulativeDelta(CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0);
}

if (BarsInProgress == 0)
{
    // Print the close of the cumulative delta bar with a delta type of Bid Ask and with a Session period
    Print("Delta Close: " + cumulativeDelta.DeltaClose[0]);
}
else if (BarsInProgress == 1)
{
    // We have to update the secondary series of the hosted indicator to make sure the values we get in BarsInProgress == 0 are in sync
    cumulativeDelta.Update(cumulativeDelta.BarsArray[1].Count - 1, 1);
}

```

## [Description](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#description)

An indicator that accumulates the volume of orders filled at bid and ask prices or up and down ticks throughout the session and compares them to determine buy/sell pressure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#syntax)

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter)`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter)`

**Returns Open value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaOpen[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaOpen[int barsAgo]`

**Returns High value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaHigh[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaHigh[int barsAgo]`

**Returns Low value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaLow[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaLow[int barsAgo]`

**Returns Close value**

`OrderFlowCumulativeDelta(CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaClose[int barsAgo]`

`OrderFlowCumulativeDelta(ISeries<double> input, CumulativeDeltaType deltaType, CumulativeDeltaPeriod period, int sizeFilter).DeltaClose[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| deltaType | The type of data to delta calculates on:<br>- BidAsk<br>- UpDownTick |
| period | The period in which the delta accumulates:<br>- Session<br>- Bar |
| sizeFilter | Input to exclude volume less than the selected value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta\#examples)

```jsx-150469391 csharp
// Calling the OrderFlowCumulativeDelta() method directly
// A 1 tick data series must be added to the OnStateChange() as this indicator runs off of tick data
else if (State == State.Configure)
{
   AddDataSeries(Data.BarsPeriodType.Tick, 1);
}

// OnBarUpdate() logic
if (BarsInProgress == 0)
{
    // Print the close of the cumulative delta bar with a delta type of Bid Ask and with a Session period
    Print("Delta Close: " + OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).DeltaClose[0]);
}
else if (BarsInProgress == 1)
{
    // We have to update the secondary series of the cached indicator to make sure the values we get in BarsInProgress == 0 are in sync
    OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).Update(OrderFlowCumulativeDelta(BarsArray[0], CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0).BarsArray[1].Count - 1, 1);
}

```

```jsx-150469391 csharp
// Calling the OrderFlowCumulativeDelta() method by reference

// A 1 tick data series must be added to OnStateChange() as this indicator runs off of tick data
else if (State == State.Configure)
{
    AddDataSeries(Data.BarsPeriodType.Tick, 1);
}
else if (State == State.DataLoaded)
{
    // Instantiate the indicator
    cumulativeDelta = OrderFlowCumulativeDelta(CumulativeDeltaType.BidAsk, CumulativeDeltaPeriod.Session, 0);
}

if (BarsInProgress == 0)
{
    // Print the close of the cumulative delta bar with a delta type of Bid Ask and with a Session period
    Print("Delta Close: " + cumulativeDelta.DeltaClose[0]);
}
else if (BarsInProgress == 1)
{
    // We have to update the secondary series of the hosted indicator to make sure the values we get in BarsInProgress == 0 are in sync
    cumulativeDelta.Update(cumulativeDelta.BarsArray[1].Count - 1, 1);
}

```