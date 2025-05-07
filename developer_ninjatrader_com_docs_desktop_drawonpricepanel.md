## [Definition](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#definition)

Determines the chart panel the draw objects renders

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#property-value)

This property returns true if the indicator paints draw objects on the price panel; otherwise when false, draw objects are painted on the actual indicator panel itself. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults**. Dynamically using **DrawOnPricePanel** in an indicator outside of **State.SetDefaults** may show issues when working with that indicator through a hosting strategy via **AddChartIndicator()**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#syntax)

`DrawOnPricePanel`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          DrawOnPricePanel = false; // Draw objects now paint on the indicator panel itself
          AddPlot(Brushes.Orange, "SMA");
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#definition)

Determines the chart panel the draw objects renders

## [Property Value](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#property-value)

This property returns true if the indicator paints draw objects on the price panel; otherwise when false, draw objects are painted on the actual indicator panel itself. Default set to true.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults**. Dynamically using **DrawOnPricePanel** in an indicator outside of **State.SetDefaults** may show issues when working with that indicator through a hosting strategy via **AddChartIndicator()**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#syntax)

`DrawOnPricePanel`

## [Examples](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          DrawOnPricePanel = false; // Draw objects now paint on the indicator panel itself
          AddPlot(Brushes.Orange, "SMA");
     }
}

```