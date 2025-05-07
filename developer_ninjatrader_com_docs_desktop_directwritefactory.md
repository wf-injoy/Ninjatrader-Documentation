## [Definition](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#definition)

Provides a default **DirectWrite** factory used for creating [**SharpDX.DirectWrite**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) components.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#property-value)

A read-only **SharpDX.DirectWrite.Factory** used to create DirectWrite objects compatible with **NinjaTrader** rendering.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#syntax)

`NinjaTrader.Core.Globals.DirectWriteFactory`

## [Examples](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#examples)

```jsx-150469391 csharp
// create a text format object with default NinjaTrader DirectWrite factory

SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(NinjaTrader.Core.Globals.DirectWriteFactory,
   "Arial", 12f);

// create a text layout object with default NinjaTrader DirectWrite factory

SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(NinjaTrader.Core.Globals.DirectWriteFactory,

   "text to render", textFormat, ChartPanel.W, ChartPanel.H);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#definition)

Provides a default **DirectWrite** factory used for creating [**SharpDX.DirectWrite**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite) components.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#property-value)

A read-only **SharpDX.DirectWrite.Factory** used to create DirectWrite objects compatible with **NinjaTrader** rendering.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#syntax)

`NinjaTrader.Core.Globals.DirectWriteFactory`

## [Examples](https://developer.ninjatrader.com/docs/desktop/directwritefactory\#examples)

```jsx-150469391 csharp
// create a text format object with default NinjaTrader DirectWrite factory

SharpDX.DirectWrite.TextFormat textFormat = new SharpDX.DirectWrite.TextFormat(NinjaTrader.Core.Globals.DirectWriteFactory,
   "Arial", 12f);

// create a text layout object with default NinjaTrader DirectWrite factory

SharpDX.DirectWrite.TextLayout textLayout = new SharpDX.DirectWrite.TextLayout(NinjaTrader.Core.Globals.DirectWriteFactory,

   "text to render", textFormat, ChartPanel.W, ChartPanel.H);

```