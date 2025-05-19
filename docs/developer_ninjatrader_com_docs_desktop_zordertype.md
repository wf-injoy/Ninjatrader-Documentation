## [Definition](https://developer.ninjatrader.com/docs/desktop/zordertype\#definition)

Determines the order in which sthe drawing tool will be rendered. This will help control the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) index between chart objects

## [Property Value](https://developer.ninjatrader.com/docs/desktop/zordertype\#property-value)

An enum determining the drawing tool's ZOrder type.  Possible values are:

| Name | Description |
| --- | --- |
| **DrawingToolZOrder.Normal** | Default behavior, drawing tools are rendered as they appear in the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) index |
| **DrawingToolZOrder.AlwaysDrawnFirst** | Ensures the drawing tool is always the first to be rendered |
| **DrawingToolZOrder.AlwaysDrawnLast** | Ensures the drawing tool is always the last object to be rendered |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/zordertype\#syntax)

`ZOrderType`

## [Examples](https://developer.ninjatrader.com/docs/desktop/zordertype\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name               = @"My Drawing Tool";

    // always draw this last
    ZOrderType           = DrawingToolZOrder.AlwaysDrawnLast;
  }
  else if (State == State.Configure)
  {
  }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/zordertype\#definition)

Determines the order in which sthe drawing tool will be rendered. This will help control the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) index between chart objects

## [Property Value](https://developer.ninjatrader.com/docs/desktop/zordertype\#property-value)

An enum determining the drawing tool's ZOrder type.  Possible values are:

| Name | Description |
| --- | --- |
| **DrawingToolZOrder.Normal** | Default behavior, drawing tools are rendered as they appear in the [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) index |
| **DrawingToolZOrder.AlwaysDrawnFirst** | Ensures the drawing tool is always the first to be rendered |
| **DrawingToolZOrder.AlwaysDrawnLast** | Ensures the drawing tool is always the last object to be rendered |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/zordertype\#syntax)

`ZOrderType`

## [Examples](https://developer.ninjatrader.com/docs/desktop/zordertype\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name               = @"My Drawing Tool";

    // always draw this last
    ZOrderType           = DrawingToolZOrder.AlwaysDrawnLast;
  }
  else if (State == State.Configure)
  {
  }
}

```