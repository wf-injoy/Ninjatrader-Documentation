## [Definition](https://developer.ninjatrader.com/docs/desktop/barsperiod\#definition)

The primary Bars object time frame (period type and interval).

## Warning

This property should NOT be accessed within the [OnStateChange](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached State.DataLoaded

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsperiod\#property-value)

A [Bars](https://developer.ninjatrader.com/docs/desktop/bars) series object representing the time frame of the Bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsperiod\#syntax)

| BarsPeriod.BarsPeriodType | The type of bars used for the period, as well as the enumeration value under which the any of the 14 default NinjaTrader types are registered. Possible values include: |
| --- | --- |
| BarsPeriodType.Tick | 0 |
| BarsPeriodType.Volume | 1 |
| BarsPeriodType.Range | 2 |
| BarsPeriodType.Second | 3 |
| BarsPeriodType.Minute | 4 |
| BarsPeriodType.Day | 5 |
| BarsPeriodType.Week | 6 |
| BarsPeriodType.Month | 7 |
| BarsPeriodType.Year | 8 |
| BarsPeriodType.HeikenAshi | 9 |
| BarsPeriodType.Kagi | 10 |
| BarsPeriodType.Renko | 11 |
| BarsPeriodType.PointAndFigure | 12 |
| BarsPeriodType.LineBreak | 13 |
| BarsPeriodType.Volumetric | 14 |

## Note

When creating custom [BarsTypes](https://developer.ninjatrader.com/docs/desktop/bars_type), it is recommended to pick high, unique enumeration value to avoid conflict from other BarsTypes that may be used by a single installation.

BarsPeriod = new BarsPeriod { BarsPeriodType = (BarsPeriodType)123456, BarsPeriodTypeName = "MyCustomBars", Value = 1 };

| BarsPeriod.BaseBarsPeriodType | Only relevant for [HeikenAshi](https://developer.ninjatrader.com/docs/desktop/addheikenashi), [Kagi](https://developer.ninjatrader.com/docs/desktop/addkagi), [LineBreak](https://developer.ninjatrader.com/docs/desktop/addlinebreak), [PointAndFigure](https://developer.ninjatrader.com/docs/desktop/addpointandfigure) and [Volumetric](https://developer.ninjatrader.com/docs/desktop/addvolumetric) Bars objects. Same possible values as BarsPeriod.BarsPeriodType |
| --- | --- |
| BarsPeriod.BaseBarsPeriodValue | Only relevant for [HeikenAshi](https://developer.ninjatrader.com/docs/desktop/addheikenashi), [Kagi](https://developer.ninjatrader.com/docs/desktop/addkagi), [LineBreak](https://developer.ninjatrader.com/docs/desktop/addlinebreak), [PointAndFigure](https://developer.ninjatrader.com/docs/desktop/addpointandfigure) and [Volumetric](https://developer.ninjatrader.com/docs/desktop/addvolumetric) Bars objects. Determines an integer value representing the basePeriodTypeValue parameter |
| BarsPeriod.MarketDataType | The data type used to build the bars. Possible values:<br>- MarketDataType.Ask<br>- MarketDataType.Bid<br>- MarketDataType.Last |
| BarsPeriod.PointAndFigurePriceType | Only relevant for PointAndFigure Bars objects. Possible values:<br>- PointAndFigurePriceType.Close<br>- PointAndFigurePriceType.HighsAndLows |
| BarsPeriod.ReversalType | Only relevant for Kagi Bars objects. Possible values:<br>- ReversalType.Percent<br>- ReversalType.Tick |
| BarsPeriod.Value | Determines an integer value representing the period parameter. When using Kagi Bars objects this represents the "reversal" parameter. When using LineBreak Bars objects this represents the "lineBreakCount" parameter. When using PointAndFigure Bars objects this represents the "boxSize" parameter. When using Renko Bars objects this represents the "brickSize" parameter |
| BarsPeriod.Value2 | Only relevant for PointAndFigure Bars objects. Determines an integer value representing the "reversal" parameter. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsperiod\#examples)

```jsx-150469391 csharp
// Checking BarsPeriod values
// Calculate only if there is a 100 tick chart or greater
protected override void OnBarUpdate()
{
     if (BarsPeriod.BarsPeriodType == BarsPeriodType.Tick && BarsPeriod.Value >= 100)
     {
         // Indicator calculation logic here
     }
}

```

```jsx-150469391 csharp
// Creating a new BarsPeriod object
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
           // add a 1440 minute apple bars object using the RTH session template
           AddDataSeries("AAPL", new BarsPeriod { BarsPeriodType = BarsPeriodType.Minute, Value = 1440 }, "US Equities RTH");
     }

     else if (State == State.DataLoaded)
     {
           // Print out the loaded bars period
           Print(Instrument.FullName + " " + BarsPeriod); // MSFT 1 Minute
           Print(BarsArray[1].Instrument.FullName + " " + BarsArray[1].BarsPeriod); // AAPL 1440 Minute
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/barsperiod\#definition)

The primary Bars object time frame (period type and interval).

## Warning

This property should NOT be accessed within the [OnStateChange](https://developer.ninjatrader.com/docs/desktop/onstatechange) method before the State has reached State.DataLoaded

## [Property Value](https://developer.ninjatrader.com/docs/desktop/barsperiod\#property-value)

A [Bars](https://developer.ninjatrader.com/docs/desktop/bars) series object representing the time frame of the Bars.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/barsperiod\#syntax)

| BarsPeriod.BarsPeriodType | The type of bars used for the period, as well as the enumeration value under which the any of the 14 default NinjaTrader types are registered. Possible values include: |
| --- | --- |
| BarsPeriodType.Tick | 0 |
| BarsPeriodType.Volume | 1 |
| BarsPeriodType.Range | 2 |
| BarsPeriodType.Second | 3 |
| BarsPeriodType.Minute | 4 |
| BarsPeriodType.Day | 5 |
| BarsPeriodType.Week | 6 |
| BarsPeriodType.Month | 7 |
| BarsPeriodType.Year | 8 |
| BarsPeriodType.HeikenAshi | 9 |
| BarsPeriodType.Kagi | 10 |
| BarsPeriodType.Renko | 11 |
| BarsPeriodType.PointAndFigure | 12 |
| BarsPeriodType.LineBreak | 13 |
| BarsPeriodType.Volumetric | 14 |

## Note

When creating custom [BarsTypes](https://developer.ninjatrader.com/docs/desktop/bars_type), it is recommended to pick high, unique enumeration value to avoid conflict from other BarsTypes that may be used by a single installation.

BarsPeriod = new BarsPeriod { BarsPeriodType = (BarsPeriodType)123456, BarsPeriodTypeName = "MyCustomBars", Value = 1 };

| BarsPeriod.BaseBarsPeriodType | Only relevant for [HeikenAshi](https://developer.ninjatrader.com/docs/desktop/addheikenashi), [Kagi](https://developer.ninjatrader.com/docs/desktop/addkagi), [LineBreak](https://developer.ninjatrader.com/docs/desktop/addlinebreak), [PointAndFigure](https://developer.ninjatrader.com/docs/desktop/addpointandfigure) and [Volumetric](https://developer.ninjatrader.com/docs/desktop/addvolumetric) Bars objects. Same possible values as BarsPeriod.BarsPeriodType |
| --- | --- |
| BarsPeriod.BaseBarsPeriodValue | Only relevant for [HeikenAshi](https://developer.ninjatrader.com/docs/desktop/addheikenashi), [Kagi](https://developer.ninjatrader.com/docs/desktop/addkagi), [LineBreak](https://developer.ninjatrader.com/docs/desktop/addlinebreak), [PointAndFigure](https://developer.ninjatrader.com/docs/desktop/addpointandfigure) and [Volumetric](https://developer.ninjatrader.com/docs/desktop/addvolumetric) Bars objects. Determines an integer value representing the basePeriodTypeValue parameter |
| BarsPeriod.MarketDataType | The data type used to build the bars. Possible values:<br>- MarketDataType.Ask<br>- MarketDataType.Bid<br>- MarketDataType.Last |
| BarsPeriod.PointAndFigurePriceType | Only relevant for PointAndFigure Bars objects. Possible values:<br>- PointAndFigurePriceType.Close<br>- PointAndFigurePriceType.HighsAndLows |
| BarsPeriod.ReversalType | Only relevant for Kagi Bars objects. Possible values:<br>- ReversalType.Percent<br>- ReversalType.Tick |
| BarsPeriod.Value | Determines an integer value representing the period parameter. When using Kagi Bars objects this represents the "reversal" parameter. When using LineBreak Bars objects this represents the "lineBreakCount" parameter. When using PointAndFigure Bars objects this represents the "boxSize" parameter. When using Renko Bars objects this represents the "brickSize" parameter |
| BarsPeriod.Value2 | Only relevant for PointAndFigure Bars objects. Determines an integer value representing the "reversal" parameter. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/barsperiod\#examples)

```jsx-150469391 csharp
// Checking BarsPeriod values
// Calculate only if there is a 100 tick chart or greater
protected override void OnBarUpdate()
{
     if (BarsPeriod.BarsPeriodType == BarsPeriodType.Tick && BarsPeriod.Value >= 100)
     {
         // Indicator calculation logic here
     }
}

```

```jsx-150469391 csharp
// Creating a new BarsPeriod object
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
           // add a 1440 minute apple bars object using the RTH session template
           AddDataSeries("AAPL", new BarsPeriod { BarsPeriodType = BarsPeriodType.Minute, Value = 1440 }, "US Equities RTH");
     }

     else if (State == State.DataLoaded)
     {
           // Print out the loaded bars period
           Print(Instrument.FullName + " " + BarsPeriod); // MSFT 1 Minute
           Print(BarsArray[1].Instrument.FullName + " " + BarsArray[1].BarsPeriod); // AAPL 1440 Minute
     }
}

```