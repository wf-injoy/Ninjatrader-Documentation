## [Definition](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#definition)

Allows to set a default ChartStyle for usage with a NinjaTrader bars type

## [Property Value](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#property-value)

A **ChartStyleType** enum value representing the [ChartStyle](https://developer.ninjatrader.com/docs/desktop/chartstyletype) to be set as default. System defaults include:

- **ChartStyleType.Box**
- **ChartStyleType.CandleStick**
- **ChartStyleType.LineOnClose**
- **ChartStyleType.OHLC**
- **ChartStyleType.PointAndFigure**
- **ChartStyleType.KagiLine**
- **ChartStyleType.OpenClose**
- **ChartStyleType.Mountain**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#syntax)

`DefaultChartStyle`

## [Examples](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name                     = "SampleBarsType";
        BarsPeriod               = new BarsPeriod { BarsPeriodType = (BarsPeriodType) 15, BarsPeriodTypeName = "SampleBarsType(15)", Value = 1 };
        BuiltFrom                = BarsPeriodType.Minute;
        DaysToLoad               = 5;
        DefaultChartStyle        = Gui.Chart.ChartStyleType.CandleStick;
        IsIntraday               = true;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#definition)

Allows to set a default ChartStyle for usage with a NinjaTrader bars type

## [Property Value](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#property-value)

A **ChartStyleType** enum value representing the [ChartStyle](https://developer.ninjatrader.com/docs/desktop/chartstyletype) to be set as default. System defaults include:

- **ChartStyleType.Box**
- **ChartStyleType.CandleStick**
- **ChartStyleType.LineOnClose**
- **ChartStyleType.OHLC**
- **ChartStyleType.PointAndFigure**
- **ChartStyleType.KagiLine**
- **ChartStyleType.OpenClose**
- **ChartStyleType.Mountain**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#syntax)

`DefaultChartStyle`

## [Examples](https://developer.ninjatrader.com/docs/desktop/defaultchartstyle\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name                     = "SampleBarsType";
        BarsPeriod               = new BarsPeriod { BarsPeriodType = (BarsPeriodType) 15, BarsPeriodTypeName = "SampleBarsType(15)", Value = 1 };
        BuiltFrom                = BarsPeriodType.Minute;
        DaysToLoad               = 5;
        DefaultChartStyle        = Gui.Chart.ChartStyleType.CandleStick;
        IsIntraday               = true;
    }
}

```