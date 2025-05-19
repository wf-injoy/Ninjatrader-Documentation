## [Definition](https://developer.ninjatrader.com/docs/desktop/isfalling\#definition)

Evaluates a falling condition which is true when the current value is less than the value of 1 bar ago.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isfalling\#method-return-value)

This method returns true if a falling condition is present; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isfalling\#syntax)

`IsFalling(ISeries<double> series)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isfalling\#parameters)

| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isfalling\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // If the 20 period SMA is falling (in downtrend) go short
   if (IsFalling(SMA(20)))
       EnterShort();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isfalling\#definition)

Evaluates a falling condition which is true when the current value is less than the value of 1 bar ago.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isfalling\#method-return-value)

This method returns true if a falling condition is present; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isfalling\#syntax)

`IsFalling(ISeries<double> series)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isfalling\#parameters)

| **series** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isfalling\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // If the 20 period SMA is falling (in downtrend) go short
   if (IsFalling(SMA(20)))
       EnterShort();
}

```