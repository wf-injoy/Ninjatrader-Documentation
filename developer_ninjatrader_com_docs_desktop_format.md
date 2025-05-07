## [Definition](https://developer.ninjatrader.com/docs/desktop/format\#definition)

This method allows you to customize the rendering of the performance value on the Summary grid.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/format\#syntax)

`public override string Format(object value, Cbi.PerformanceUnit unit, string propertyName)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/format\#examples)

```jsx-150469391 csharp
public override string Format(object value, Cbi.PerformanceUnit unit, string propertyName)
{
    double[] tmp = value as double[];
    if (tmp != null && tmp.Length == 5)
        switch (unit)
        {
          case Cbi.PerformanceUnit.Currency : return Core.Globals.FormatCurrency(tmp[0], denomination);
          case Cbi.PerformanceUnit.Percent   : return tmp[1].ToString("P");
          case Cbi.PerformanceUnit.Pips : return Math.Round(tmp[2]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
          case Cbi.PerformanceUnit.Points : return Math.Round(tmp[3]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
          case Cbi.PerformanceUnit.Ticks : return Math.Round(tmp[4]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
        }
    return value.ToString();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/format\#definition)

This method allows you to customize the rendering of the performance value on the Summary grid.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/format\#syntax)

`public override string Format(object value, Cbi.PerformanceUnit unit, string propertyName)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/format\#examples)

```jsx-150469391 csharp
public override string Format(object value, Cbi.PerformanceUnit unit, string propertyName)
{
    double[] tmp = value as double[];
    if (tmp != null && tmp.Length == 5)
        switch (unit)
        {
          case Cbi.PerformanceUnit.Currency : return Core.Globals.FormatCurrency(tmp[0], denomination);
          case Cbi.PerformanceUnit.Percent   : return tmp[1].ToString("P");
          case Cbi.PerformanceUnit.Pips : return Math.Round(tmp[2]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
          case Cbi.PerformanceUnit.Points : return Math.Round(tmp[3]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
          case Cbi.PerformanceUnit.Ticks : return Math.Round(tmp[4]).ToString(Core.Globals.GeneralOptions.CurrentCulture);
        }
    return value.ToString();
}

```