## [Definition](https://developer.ninjatrader.com/docs/desktop/tovector2\#definition)

Converts a **System.Windows.Point** structure to a **SharpDX.Vector2** when [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/tovector2\#method-return-value)

A new **SharpDX.Vector2** constructed with the point parameters X and Y values.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/tovector2\#syntax)

`DxExtensions.ToVector2(this System.Windows.Point point)`

`<point>.ToVector2()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/tovector2\#parameters)

| point | The [System.Windows.Point](https://msdn.microsoft.com/en-us/library/system.windows.point(v=vs.110).aspx) point to convert |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tovector2\#examples)

```jsx-150469391 csharp
// gets the application/user WPF point and converts to a SharpDX Vector
System.Windows.Point wpfPoint = ChartControl.MouseDownPoint;

SharpDX.Vector2 dxVector2 = wpfPoint.ToVector2();

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/tovector2\#definition)

Converts a **System.Windows.Point** structure to a **SharpDX.Vector2** when [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/tovector2\#method-return-value)

A new **SharpDX.Vector2** constructed with the point parameters X and Y values.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/tovector2\#syntax)

`DxExtensions.ToVector2(this System.Windows.Point point)`

`<point>.ToVector2()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/tovector2\#parameters)

| point | The [System.Windows.Point](https://msdn.microsoft.com/en-us/library/system.windows.point(v=vs.110).aspx) point to convert |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tovector2\#examples)

```jsx-150469391 csharp
// gets the application/user WPF point and converts to a SharpDX Vector
System.Windows.Point wpfPoint = ChartControl.MouseDownPoint;

SharpDX.Vector2 dxVector2 = wpfPoint.ToVector2();

```