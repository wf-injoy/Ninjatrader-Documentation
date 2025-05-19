## [Definition](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#definition)

Sets the default base values used for the **BarsPeriod** selected by the user (e.g., the default PeriodValue, DaysToLoad, etc.) for your custom Bar Type.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#parameters)

| period | The **BarsPeriod** chosen by the user when utilizing this Bars type |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#syntax)

You must override the method in your Bars Type with the following syntax:

`public override void ApplyDefaultBasePeriodValue(BarsPeriod period) { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#examples)

```jsx-150469391 csharp
public override void ApplyDefaultBasePeriodValue(BarsPeriod period)
{
    //sets the default Minute bars period value to 1, and days to load to 5
    if (period.BaseBarsPeriodType == BarsPeriodType.Minute)
    {
        period.BaseBarsPeriodValue = 1;
        DaysToLoad = 5;
    }
    //sets the default Tick bars period value to 150, and days to load to 3
    else if (period.BaseBarsPeriodType == BarsPeriodType.Tick)
    {
        period.BaseBarsPeriodValue = 150;
        DaysToLoad = 3;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#definition)

Sets the default base values used for the **BarsPeriod** selected by the user (e.g., the default PeriodValue, DaysToLoad, etc.) for your custom Bar Type.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#parameters)

| period | The **BarsPeriod** chosen by the user when utilizing this Bars type |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#syntax)

You must override the method in your Bars Type with the following syntax:

`public override void ApplyDefaultBasePeriodValue(BarsPeriod period) { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/applydefaultbaseperiodvalue\#examples)

```jsx-150469391 csharp
public override void ApplyDefaultBasePeriodValue(BarsPeriod period)
{
    //sets the default Minute bars period value to 1, and days to load to 5
    if (period.BaseBarsPeriodType == BarsPeriodType.Minute)
    {
        period.BaseBarsPeriodValue = 1;
        DaysToLoad = 5;
    }
    //sets the default Tick bars period value to 150, and days to load to 3
    else if (period.BaseBarsPeriodType == BarsPeriodType.Tick)
    {
        period.BaseBarsPeriodValue = 150;
        DaysToLoad = 3;
    }
}

```