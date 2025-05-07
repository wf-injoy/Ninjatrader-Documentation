## [Definition](https://developer.ninjatrader.com/docs/desktop/today\#definition)

Calculates an integer value representing a date.

## Note

Integer representation of day is format as yyyyMMdd where January 8, 2015 would be 20150108.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/today\#method-return-value)

An **int** value representing date structure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/today\#syntax)

`ToDay(DateTime time)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/today\#parameters)

| Parameter | Description |
| --- | --- |
| **time** | A DateTime structure to calculate. Note: See also the [Time](https://developer.ninjatrader.com/docs/desktop/time) property. |

## Note

Tip: NinjaScript uses the .NET [DateTime](http://msdn2.microsoft.com/en-us/library/system.datetime.aspx) structures which can be complicated for novice programmers. If you are familiar with **C#** you can directly use DateTime structure properties and methods for date and time comparisons otherwise use this method and the [ToTime()](https://developer.ninjatrader.com/docs/desktop/totime) method.

## [Examples](https://developer.ninjatrader.com/docs/desktop/today\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Compare the date of the current bar to September 15, 2014
    if (ToDay(Time[0]) > 20140915)
    {
        // Do something
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/today\#definition)

Calculates an integer value representing a date.

## Note

Integer representation of day is format as yyyyMMdd where January 8, 2015 would be 20150108.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/today\#method-return-value)

An **int** value representing date structure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/today\#syntax)

`ToDay(DateTime time)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/today\#parameters)

| Parameter | Description |
| --- | --- |
| **time** | A DateTime structure to calculate. Note: See also the [Time](https://developer.ninjatrader.com/docs/desktop/time) property. |

## Note

Tip: NinjaScript uses the .NET [DateTime](http://msdn2.microsoft.com/en-us/library/system.datetime.aspx) structures which can be complicated for novice programmers. If you are familiar with **C#** you can directly use DateTime structure properties and methods for date and time comparisons otherwise use this method and the [ToTime()](https://developer.ninjatrader.com/docs/desktop/totime) method.

## [Examples](https://developer.ninjatrader.com/docs/desktop/today\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    // Compare the date of the current bar to September 15, 2014
    if (ToDay(Time[0]) > 20140915)
    {
        // Do something
    }
}

```