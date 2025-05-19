## [Definition](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#definition)

Determines the value your **BarsType** would return for [**Bars.PercentComplete**](https://developer.ninjatrader.com/docs/desktop/percentcomplete).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#method-return-value)

This method returns A **double** value.

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#method-parameters)

| **bars** | The [**bars**](https://developer.ninjatrader.com/docs/desktop/bars) object chosen by the user when utilizing this Bars type |
| **now** | The **DateTime** value to measure |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#syntax)

You must override the method in your Bars Type with the following syntax.

`public override double GetPercentComplete(Bars bars, DateTime now) {  }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#examples)

```jsx-150469391 csharp
public override double GetPercentComplete(Bars bars, DateTime now)
{
     // Calculate the percent complete for our monthly bars
     if (now.Date <= bars.LastBarTime.Date)
     {
         int month = now.Month;
         int daysInMonth = (month == 2) ? (DateTime.IsLeapYear(now.Year) ? 29 : 28) :
               (month == 1 || month == 3 || month == 5 || month == 7 || month == 8 || month == 10 || month == 12 ? 31 : 30);
         return (daysInMonth - (barsSeries.LastBarTime.Date.AddDays(1).Subtract(now).TotalDays / barsSeries.BarsPeriod.Value)) /
               daysInMonth; // an estimate
     }
     return 1;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#definition)

Determines the value your **BarsType** would return for [**Bars.PercentComplete**](https://developer.ninjatrader.com/docs/desktop/percentcomplete).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#method-return-value)

This method returns A **double** value.

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#method-parameters)

| **bars** | The [**bars**](https://developer.ninjatrader.com/docs/desktop/bars) object chosen by the user when utilizing this Bars type |
| **now** | The **DateTime** value to measure |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#syntax)

You must override the method in your Bars Type with the following syntax.

`public override double GetPercentComplete(Bars bars, DateTime now) {  }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/getpercentcomplete\#examples)

```jsx-150469391 csharp
public override double GetPercentComplete(Bars bars, DateTime now)
{
     // Calculate the percent complete for our monthly bars
     if (now.Date <= bars.LastBarTime.Date)
     {
         int month = now.Month;
         int daysInMonth = (month == 2) ? (DateTime.IsLeapYear(now.Year) ? 29 : 28) :
               (month == 1 || month == 3 || month == 5 || month == 7 || month == 8 || month == 10 || month == 12 ? 31 : 30);
         return (daysInMonth - (barsSeries.LastBarTime.Date.AddDays(1).Subtract(now).TotalDays / barsSeries.BarsPeriod.Value)) /
               daysInMonth; // an estimate
     }
     return 1;
}

```