## [Definition](https://developer.ninjatrader.com/docs/desktop/isrising\#definition)

Evaluates a rising condition which is true when the current value is greater than the value of 1 bar ago.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isrising\#method-return-value)

This method returns true if a rising condition is present; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isrising\#syntax)

`IsRising(ISeries<double> series)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isrising\#parameters)

| Parameter | Description |
| --- | --- |
| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isrising\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // If the 20 period SMA is rising (in uptrend) go long
   if (IsRising(SMA(20)))
       EnterLong();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isrising\#definition)

Evaluates a rising condition which is true when the current value is greater than the value of 1 bar ago.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isrising\#method-return-value)

This method returns true if a rising condition is present; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isrising\#syntax)

`IsRising(ISeries<double> series)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isrising\#parameters)

| Parameter | Description |
| --- | --- |
| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isrising\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // If the 20 period SMA is rising (in uptrend) go long
   if (IsRising(SMA(20)))
       EnterLong();
}

```