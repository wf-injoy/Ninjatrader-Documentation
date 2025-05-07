## [Definition](https://developer.ninjatrader.com/docs/desktop/oncopyto\#definition)

Called as the values of a trade metric are saved.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncopyto\#syntax)

`protected override void OnCopyTo(PerformanceMetricBase target) { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncopyto\#examples)

```jsx-150469391 csharp
protected override void OnCopyTo(PerformanceMetricBase target)
{
   // You need to cast, in order to access the right type
   SampleCumProfit targetMetrics = (target as SampleCumProfit);
   if (targetMetrics != null)
     Array.Copy(Values, targetMetrics.Values, Values.Length);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/oncopyto\#definition)

Called as the values of a trade metric are saved.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/oncopyto\#syntax)

`protected override void OnCopyTo(PerformanceMetricBase target) { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/oncopyto\#examples)

```jsx-150469391 csharp
protected override void OnCopyTo(PerformanceMetricBase target)
{
   // You need to cast, in order to access the right type
   SampleCumProfit targetMetrics = (target as SampleCumProfit);
   if (targetMetrics != null)
     Array.Copy(Values, targetMetrics.Values, Values.Length);
}

```