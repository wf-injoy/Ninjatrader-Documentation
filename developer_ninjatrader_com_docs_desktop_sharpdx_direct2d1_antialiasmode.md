## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#definition)

Specifies how the edges of nontext primitives are rendered.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368061.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#syntax)

`enum AntialiasMode`

## [Enumerators](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#enumerators)

| Enumerator | Description |
| --- | --- |
| **PerPrimitive** | Edges are antialiased using the Direct2D per-primitive method of high-quality antialiasing. |
| **Aliased** | Objects are aliased in most cases. Objects are antialiased only when they are drawn to a render target created by the CreateDxgiSurfaceRenderTarget method and Direct3D multisampling has been enabled on the backing DirectX Graphics Infrastructure (DXGI) surface. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#definition)

Specifies how the edges of nontext primitives are rendered.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd368061.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#syntax)

`enum AntialiasMode`

## [Enumerators](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_antialiasmode\#enumerators)

| Enumerator | Description |
| --- | --- |
| **PerPrimitive** | Edges are antialiased using the Direct2D per-primitive method of high-quality antialiasing. |
| **Aliased** | Objects are aliased in most cases. Objects are antialiased only when they are drawn to a render target created by the CreateDxgiSurfaceRenderTarget method and Direct3D multisampling has been enabled on the backing DirectX Graphics Infrastructure (DXGI) surface. |