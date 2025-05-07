The **ChartBars** class provides GUI access related methods and properties to the primary bars series configured on the Chart through the [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) menu. For data access information related to the NinjaScript input's bars series, please use the [Bars Series](https://developer.ninjatrader.com/docs/desktop/bars) object (or the [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) for multi-series input).

## Note

A ChartBars object will ONLY exist should the hosting NinjaScript type be loaded through a [Chart](https://developer.ninjatrader.com/docs/desktop/charts). For example, a Strategy would have access to a ChartBars property when running on a Chart, but would NOT when loaded through the [Strategies Grid](https://ninjatrader.com/support/helpGuides/nt8/?strategies_tab2.htm) or [Strategy analyzer](https://ninjatrader.com/support/helpGuides/nt8/?strategy_analyzer.htm).

## Warning

It is crucial to check for object references before accessing the ChartBars otherwise possible null reference errors can be expected depending on where the NinjaScript object was started. See example below.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartbars\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Bars](https://developer.ninjatrader.com/docs/desktop/chartbars_bars) | Data returned from the historical data repository. |
| [Count](https://developer.ninjatrader.com/docs/desktop/chartbars_count) | The total number of ChartBars that exist on the chart. |
| [FromIndex](https://developer.ninjatrader.com/docs/desktop/fromindex) | An index value representing the first bar painted on the chart. |
| [GetBarIdxByTime()](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime) | An ChartBar index value calculated from a time value on the chart. |
| [GetBarIdxByX()](https://developer.ninjatrader.com/docs/desktop/getbaridxbyx) | Returns the ChartBar index value at a specified x-coordinate relative to the ChartControl. |
| [GetTimeByBarIdx()](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx) | The ChartBars time value calculated from a bar index value on the chart. |
| [Panel](https://developer.ninjatrader.com/docs/desktop/panel) | The Panel index value that the ChartBars reside. |
| [Properties](https://developer.ninjatrader.com/docs/desktop/chartbars_properties) | Various ChartBar properties that have been configured from the Chart's [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) menu. |
| [ToChartString()](https://developer.ninjatrader.com/docs/desktop/tochartstring) | A string formatted for the Chart's Data Series Label as well as the period. |
| [ToIndex](https://developer.ninjatrader.com/docs/desktop/toindex) | An index value representing the last bar painted on the chart. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartbars\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
     if(ChartBars != null)
     {
         Print("The starting number of bars on the chart is " + ChartBars.Bars.Count);
     }
     else
     {
         Print("Strategy was not loaded from a chart, exiting strategy...");
         return;
     }
   }
}

```

The **ChartBars** class provides GUI access related methods and properties to the primary bars series configured on the Chart through the [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) menu. For data access information related to the NinjaScript input's bars series, please use the [Bars Series](https://developer.ninjatrader.com/docs/desktop/bars) object (or the [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) for multi-series input).

## Note

A ChartBars object will ONLY exist should the hosting NinjaScript type be loaded through a [Chart](https://developer.ninjatrader.com/docs/desktop/charts). For example, a Strategy would have access to a ChartBars property when running on a Chart, but would NOT when loaded through the [Strategies Grid](https://ninjatrader.com/support/helpGuides/nt8/?strategies_tab2.htm) or [Strategy analyzer](https://ninjatrader.com/support/helpGuides/nt8/?strategy_analyzer.htm).

## Warning

It is crucial to check for object references before accessing the ChartBars otherwise possible null reference errors can be expected depending on where the NinjaScript object was started. See example below.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartbars\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [Bars](https://developer.ninjatrader.com/docs/desktop/chartbars_bars) | Data returned from the historical data repository. |
| [Count](https://developer.ninjatrader.com/docs/desktop/chartbars_count) | The total number of ChartBars that exist on the chart. |
| [FromIndex](https://developer.ninjatrader.com/docs/desktop/fromindex) | An index value representing the first bar painted on the chart. |
| [GetBarIdxByTime()](https://developer.ninjatrader.com/docs/desktop/getbaridxbytime) | An ChartBar index value calculated from a time value on the chart. |
| [GetBarIdxByX()](https://developer.ninjatrader.com/docs/desktop/getbaridxbyx) | Returns the ChartBar index value at a specified x-coordinate relative to the ChartControl. |
| [GetTimeByBarIdx()](https://developer.ninjatrader.com/docs/desktop/gettimebybaridx) | The ChartBars time value calculated from a bar index value on the chart. |
| [Panel](https://developer.ninjatrader.com/docs/desktop/panel) | The Panel index value that the ChartBars reside. |
| [Properties](https://developer.ninjatrader.com/docs/desktop/chartbars_properties) | Various ChartBar properties that have been configured from the Chart's [Data Series](https://ninjatrader.com/support/helpGuides/nt8/?working_with_price_data.htm) menu. |
| [ToChartString()](https://developer.ninjatrader.com/docs/desktop/tochartstring) | A string formatted for the Chart's Data Series Label as well as the period. |
| [ToIndex](https://developer.ninjatrader.com/docs/desktop/toindex) | An index value representing the last bar painted on the chart. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartbars\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
     if(ChartBars != null)
     {
         Print("The starting number of bars on the chart is " + ChartBars.Bars.Count);
     }
     else
     {
         Print("Strategy was not loaded from a chart, exiting strategy...");
         return;
     }
   }
}

```