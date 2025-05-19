## [Definition](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#definition)

Indicates if the specified input is set at a barsAgo value relative to the current bar. Please also see the **[Reset()](https://developer.ninjatrader.com/docs/desktop/reset)** method for more information.

## Note

- If called directly from the instance of the **NinjaScript** object, the value returned corresponds to the Input Series (e.g., Close, High, Low, SMA, etc.)
- When checking a **[Bar](https://developer.ninjatrader.com/docs/desktop/bars)** or **[PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries)**, `IsValidDataPoint()` returns true as long as the barsAgo value falls between 0 and the total count for that series. These are special series which always contain a value set at every slot index for multi-series scripting purposes (e.g., comparing two price series with various session templates, or one series has more ticks than the other)
- For a **[Value](https://developer.ninjatrader.com/docs/desktop/value)** series or custom **[Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest)**, `IsValidDataPoint()` returns true or false depending on if you have set a value at that index location

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#method-return-value)

A bool value, when true indicates that specified data point is set; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#syntax)

`IsValidDataPoint(int barsAgo)`

`ISeries<t>.IsValidDataPoint(int barsAgo)`

## Warning

- Calling `IsValidDataPoint()` will only work on a MaximumBarsLookBackInfinite series. Attempting to check **IsValidDataPoint()** on MaximumBarsLookBack256 series will throw an error. Please check the Log tab of the Control Center. In addition, since this method references barsAgo data, it cannot be used during **[OnRender (see note 5)](https://developer.ninjatrader.com/docs/desktop/onrender)** \- instead please use the **[IsValidDataPointAt](https://developer.ninjatrader.com/docs/desktop/isvaliddatapointat)** during OnRender.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#parameters)

| barsAgo | An int representing from the current bar the number of historical bars the method will check. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // only set plot value if hosted indicator is not reset
   if(SMA(20).IsValidDataPoint(0))
     MyPlot[0] = SMA(20)[0];
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#definition)

Indicates if the specified input is set at a barsAgo value relative to the current bar. Please also see the **[Reset()](https://developer.ninjatrader.com/docs/desktop/reset)** method for more information.

## Note

- If called directly from the instance of the **NinjaScript** object, the value returned corresponds to the Input Series (e.g., Close, High, Low, SMA, etc.)
- When checking a **[Bar](https://developer.ninjatrader.com/docs/desktop/bars)** or **[PriceSeries](https://developer.ninjatrader.com/docs/desktop/priceseries)**, `IsValidDataPoint()` returns true as long as the barsAgo value falls between 0 and the total count for that series. These are special series which always contain a value set at every slot index for multi-series scripting purposes (e.g., comparing two price series with various session templates, or one series has more ticks than the other)
- For a **[Value](https://developer.ninjatrader.com/docs/desktop/value)** series or custom **[Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest)**, `IsValidDataPoint()` returns true or false depending on if you have set a value at that index location

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#method-return-value)

A bool value, when true indicates that specified data point is set; otherwise false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#syntax)

`IsValidDataPoint(int barsAgo)`

`ISeries<t>.IsValidDataPoint(int barsAgo)`

## Warning

- Calling `IsValidDataPoint()` will only work on a MaximumBarsLookBackInfinite series. Attempting to check **IsValidDataPoint()** on MaximumBarsLookBack256 series will throw an error. Please check the Log tab of the Control Center. In addition, since this method references barsAgo data, it cannot be used during **[OnRender (see note 5)](https://developer.ninjatrader.com/docs/desktop/onrender)** \- instead please use the **[IsValidDataPointAt](https://developer.ninjatrader.com/docs/desktop/isvaliddatapointat)** during OnRender.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#parameters)

| barsAgo | An int representing from the current bar the number of historical bars the method will check. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/isvaliddatapoint\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // only set plot value if hosted indicator is not reset
   if(SMA(20).IsValidDataPoint(0))
     MyPlot[0] = SMA(20)[0];
}

```