## [Definition](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#definition)

Returns the end date and time of the previous trading session regarding the time passed in the methods parameters.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#method-return-value)

A **DateTime** structure representing the previous trading days end date and time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#syntax)

`GetPreviousTradingDayEnd(DateTime timeLocal)`

## Warning

This method is resource intensive and should ONLY be reserved for situations when calculations would be limited to a few specific use cases. For example, calling this method for each bar in the `OnBarUpdate()` method would NOT be recommended.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#parameters)

| Parameter | Description |
| --- | --- |
| **timeLocal** | An **DateTime** structure which is used to calculate the current trading day |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (Bars.IsFirstBarOfSession)
    {
        DateTime previousEndDate = TradingHours.GetPreviousTradingDayEnd(Time[0]);

        Print(string.Format("The current bars date is {0} - the previous trading session ended on {1}", Time[0], previousEndDate));
    }
    //Output:  The current bars date is 2/18/2015 12:35:00 PM - the previous trading session ended on 2/17/2015 3:15:00 PM
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#definition)

Returns the end date and time of the previous trading session regarding the time passed in the methods parameters.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#method-return-value)

A **DateTime** structure representing the previous trading days end date and time.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#syntax)

`GetPreviousTradingDayEnd(DateTime timeLocal)`

## Warning

This method is resource intensive and should ONLY be reserved for situations when calculations would be limited to a few specific use cases. For example, calling this method for each bar in the `OnBarUpdate()` method would NOT be recommended.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#parameters)

| Parameter | Description |
| --- | --- |
| **timeLocal** | An **DateTime** structure which is used to calculate the current trading day |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getprevioustradingdayend\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (Bars.IsFirstBarOfSession)
    {
        DateTime previousEndDate = TradingHours.GetPreviousTradingDayEnd(Time[0]);

        Print(string.Format("The current bars date is {0} - the previous trading session ended on {1}", Time[0], previousEndDate));
    }
    //Output:  The current bars date is 2/18/2015 12:35:00 PM - the previous trading session ended on 2/17/2015 3:15:00 PM
}

```