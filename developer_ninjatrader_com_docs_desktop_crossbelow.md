## [Definition](https://developer.ninjatrader.com/docs/desktop/crossbelow\#definition)

Evaluates a cross below condition over the specified bar look-back period.

## Note

This method does not return true if both series being compared have equal values on the current or previous bar with a lookbackPeriod of 1.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/crossbelow\#method-return-value)

This method returns true if a cross below condition occurred; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/crossbelow\#syntax)

`CrossBelow(ISeries<double> series1, ISeries<double> series2, int lookBackPeriod)`

`CrossBelow(ISeries<double> series1, double value, int lookBackPeriod)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/crossbelow\#parameters)

| Parameter | Description |
| --- | --- |
| **lookBackPeriod** | Number of bars back to check the cross below condition |
| **series1** & **series2** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |
| **value** | Any **double** value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/crossbelow\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Go long if CCI crossed below -250 within the last bar
   if (CrossBelow(CCI(14), -250, 1))
       EnterLong();

   // Go short if 10 EMA crosses below 20 EMA within the last bar
   if (CrossBelow(EMA(10), EMA(20), 1))
       EnterShort();

   // Go short we have a down bar and the 10 EMA crosses below 20 EMA within the last 5 bars
   if (Close[0] < Open[0] && CrossBelow(EMA(10), EMA(20), 5))
       EnterShort();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/crossbelow\#definition)

Evaluates a cross below condition over the specified bar look-back period.

## Note

This method does not return true if both series being compared have equal values on the current or previous bar with a lookbackPeriod of 1.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/crossbelow\#method-return-value)

This method returns true if a cross below condition occurred; otherwise, false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/crossbelow\#syntax)

`CrossBelow(ISeries<double> series1, ISeries<double> series2, int lookBackPeriod)`

`CrossBelow(ISeries<double> series1, double value, int lookBackPeriod)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/crossbelow\#parameters)

| Parameter | Description |
| --- | --- |
| **lookBackPeriod** | Number of bars back to check the cross below condition |
| **series1** & **series2** | Any **Series< `double` >** type object such as an indicator, Close, High, Low, etc... |
| **value** | Any **double** value |

## [Examples](https://developer.ninjatrader.com/docs/desktop/crossbelow\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Go long if CCI crossed below -250 within the last bar
   if (CrossBelow(CCI(14), -250, 1))
       EnterLong();

   // Go short if 10 EMA crosses below 20 EMA within the last bar
   if (CrossBelow(EMA(10), EMA(20), 1))
       EnterShort();

   // Go short we have a down bar and the 10 EMA crosses below 20 EMA within the last 5 bars
   if (Close[0] < Open[0] && CrossBelow(EMA(10), EMA(20), 5))
       EnterShort();
}

```