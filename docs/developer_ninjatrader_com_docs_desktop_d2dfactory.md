## [Definition](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#definition)

Provides a default Direct2D1 factory used for creating **SharpDX.Direct2D1** components.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#property-value)

A read-only **SharpDX.Direct2D1.Factory** to create Direct2D1 objects compatible with NinjaTrader rendering.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#syntax)

`NinjaTrader.Core.Globals.D2DFactory`

## Warning

Warning: Please ensure this property would only be accessed from `OnRender()` or `OnRenderTargetChanged()` (which run in the UI thread), as access from other threads outside those methods could cause a degradation in performance.

```jsx-150469391 csharp
// create a Direct2D1 PathGeometry format object with default NinjaTrader D2DFactory factory
SharpDX.Direct2D1.PathGeometry pathGeometry = new SharpDX.Direct2D1.PathGeometry(NinjaTrader.Core.Globals.D2DFactory);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#definition)

Provides a default Direct2D1 factory used for creating **SharpDX.Direct2D1** components.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#property-value)

A read-only **SharpDX.Direct2D1.Factory** to create Direct2D1 objects compatible with NinjaTrader rendering.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/d2dfactory\#syntax)

`NinjaTrader.Core.Globals.D2DFactory`

## Warning

Warning: Please ensure this property would only be accessed from `OnRender()` or `OnRenderTargetChanged()` (which run in the UI thread), as access from other threads outside those methods could cause a degradation in performance.

```jsx-150469391 csharp
// create a Direct2D1 PathGeometry format object with default NinjaTrader D2DFactory factory
SharpDX.Direct2D1.PathGeometry pathGeometry = new SharpDX.Direct2D1.PathGeometry(NinjaTrader.Core.Globals.D2DFactory);

```