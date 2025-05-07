## [Definition](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#definition)

Adds an indicator to the strategy only for the purpose of displaying it on a chart.

## Note

- Only the Plot properties of an indicator added by AddChartIndicator() will be accessible in the Indicators dialogue on charts. Other properties must be set in code.
- To add Bars objects to your strategy for calculation purposes see the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method.
- An indicator being added via AddChartIndicator() cannot use any additional data series hosted by the calling strategy, but can only use the strategy's primary data series. If you wish to use a different data series for the indicator's input, you can add the series in the indicator itself and explicitly reference it in the indicator code (please make sure though the hosting strategy has the same [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) call included as well)
- If a secondary or null Bars series is specified by the calling strategy (not the indicator itself), the strategy's primary series will be substituted instead.
- Dynamically using [DrawOnPricePanel](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel) in an indicator outside of State.SetDefaults may show issues when working with that indicator through a hosting strategy via AddChartIndicator().

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#syntax)

`AddChartIndicator(IndicatorBase indicator)`

## Warning

This method should ONLY be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.DataLoaded

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#parameters)

| indicator | An indicator object |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.DataLoaded)
     {
         // Charts a 20 period simple moving average to the chart
         AddChartIndicator(SMA(20));
     }
}

```

## Note

If you are adding an indicator which is dependent on the correct [State](https://developer.ninjatrader.com/docs/desktop/state) of the indicator, you will need to ensure that you are also calling the indicator from the strategy in [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate), otherwise your indicator will only process in State.RealTime for performance optimizations.

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
     // Charts a 20 period simple moving average to the chart
     AddChartIndicator(SMA(20));
   }
}

protected override void OnBarUpdate()
{
   // call SMA() historically to ensure the indicator processes its historical states as well
   double sma = SMA(20)[0];
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#definition)

Adds an indicator to the strategy only for the purpose of displaying it on a chart.

## Note

- Only the Plot properties of an indicator added by AddChartIndicator() will be accessible in the Indicators dialogue on charts. Other properties must be set in code.
- To add Bars objects to your strategy for calculation purposes see the [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) method.
- An indicator being added via AddChartIndicator() cannot use any additional data series hosted by the calling strategy, but can only use the strategy's primary data series. If you wish to use a different data series for the indicator's input, you can add the series in the indicator itself and explicitly reference it in the indicator code (please make sure though the hosting strategy has the same [AddDataSeries()](https://developer.ninjatrader.com/docs/desktop/adddataseries) call included as well)
- If a secondary or null Bars series is specified by the calling strategy (not the indicator itself), the strategy's primary series will be substituted instead.
- Dynamically using [DrawOnPricePanel](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel) in an indicator outside of State.SetDefaults may show issues when working with that indicator through a hosting strategy via AddChartIndicator().

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#syntax)

`AddChartIndicator(IndicatorBase indicator)`

## Warning

This method should ONLY be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.DataLoaded

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#parameters)

| indicator | An indicator object |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addchartindicator\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.DataLoaded)
     {
         // Charts a 20 period simple moving average to the chart
         AddChartIndicator(SMA(20));
     }
}

```

## Note

If you are adding an indicator which is dependent on the correct [State](https://developer.ninjatrader.com/docs/desktop/state) of the indicator, you will need to ensure that you are also calling the indicator from the strategy in [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate), otherwise your indicator will only process in State.RealTime for performance optimizations.

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.DataLoaded)
   {
     // Charts a 20 period simple moving average to the chart
     AddChartIndicator(SMA(20));
   }
}

protected override void OnBarUpdate()
{
   // call SMA() historically to ensure the indicator processes its historical states as well
   double sma = SMA(20)[0];
}

```