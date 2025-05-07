## [Definition](https://developer.ninjatrader.com/docs/desktop/setzorder\#definition)

Used to assign a unique identifier representing the index in which chart objects are drawn on the chart's Z-axis (front to back ordering). Objects with a higher **ZOrder** are drawn first.

## Note

1. To check on which **ZOrder** index the object gets drawn use the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) property.
2. Assigning specific **ZOrder** indices to draw at should be done once the [State](https://developer.ninjatrader.com/docs/desktop/onstatechange) has reached **State.Historical**.
3. If you want to draw your object behind the bars, assign to use index -1 (like in the example below).
4. If you want to draw your object topmost, assign to use index **int.MaxValue**.
5. Any levels in between can be directly assigned, the starting / default levels used by NinjaTrader can be seen [here](https://developer.ninjatrader.com/docs/desktop/chart_zorder).
6. You can see the highest **ZOrder** currently in a chart with code such our second example below - setting higher values than this value will result in the **ZOrder** to be set to this value, so this can be thought of as the current 'top'.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/setzorder\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setzorder\#syntax)

`SetZOrder(int DesiredZOrderLevel)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/setzorder\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.Historical)
   {
       // Make sure our object plots behind the chart bars
       SetZOrder(-1);
   }
}

```

```jsx-150469391 csharp
protected override void OnRender(ChartControl cc, ChartScale cs)
{
   Print(ChartPanel.ChartObjects.Max(co => co.ZOrder));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/setzorder\#definition)

Used to assign a unique identifier representing the index in which chart objects are drawn on the chart's Z-axis (front to back ordering). Objects with a higher **ZOrder** are drawn first.

## Note

1. To check on which **ZOrder** index the object gets drawn use the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) property.
2. Assigning specific **ZOrder** indices to draw at should be done once the [State](https://developer.ninjatrader.com/docs/desktop/onstatechange) has reached **State.Historical**.
3. If you want to draw your object behind the bars, assign to use index -1 (like in the example below).
4. If you want to draw your object topmost, assign to use index **int.MaxValue**.
5. Any levels in between can be directly assigned, the starting / default levels used by NinjaTrader can be seen [here](https://developer.ninjatrader.com/docs/desktop/chart_zorder).
6. You can see the highest **ZOrder** currently in a chart with code such our second example below - setting higher values than this value will result in the **ZOrder** to be set to this value, so this can be thought of as the current 'top'.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/setzorder\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setzorder\#syntax)

`SetZOrder(int DesiredZOrderLevel)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/setzorder\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.Historical)
   {
       // Make sure our object plots behind the chart bars
       SetZOrder(-1);
   }
}

```

```jsx-150469391 csharp
protected override void OnRender(ChartControl cc, ChartScale cs)
{
   Print(ChartPanel.ChartObjects.Max(co => co.ZOrder));
}

```