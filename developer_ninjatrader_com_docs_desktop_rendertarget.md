## [Definition](https://developer.ninjatrader.com/docs/desktop/rendertarget\#definition)

A **SharpDX Direct2D1 RenderTarget** creates objects and exposes methods used for drawing in the chart area.

## Note

Notes:

1. There are two RenderTarget's used in a chart. This is important to understand when creating/destroying device resources. Please see the [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) page for more information.
2. For a walk through for using the SharpDX RenderTarget, please see the educational resource [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/rendertarget\#property-value)

A [SharpDX.Direct2D1.RenderTarget](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget)

| Property | Description |
| --- | --- |
| **SharpDX.Direct2D1.WindowRenderTarget** | Used to render the actual contents of the chart to the window |
| **SharpDX.Direct2D1.WicRenderTarget** | Used to render a bitmap for a few scenarios:<br>1. A user clicks on a chart area; a bitmap is used to do any hit detection to determine where the user clicked.<br>2. User clicks on the Windows task bar; a bitmap is used to render the preview of the contents of the chart display through a thumbnail on the task bar.<br>3. A user re-sizes the chart; a bitmap is used to render the current contents of the chart, which is redrawn using the WindowRenderTarget after the desired changes have been set. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rendertarget\#syntax)

`RenderTarget`

## Warning

Warning: Each DirectX render target requires its own brushes. You must create brushes directly in [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or using [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrestorevalues). If you do not, you will receive an error at run time similar to:

"A direct X error has occurred while rendering the chart: HRESULT: \[0x88990015\], Module: \[SharpDX.Direct2D1\], ApiCode: \[D2DERR\_WRONG\_RESOURCE\_DOMAIN/WrongResourceDomain\], Message: The resource was realized on the wrong render target. : Each DirectX render target requires its own brushes. You must create brushes directly in OnRender() or using OnRenderTargetChanged().

Please see [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) for examples with brushes that need to be recalculated, or [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) for an example of recreating a static brush.

## [Definition](https://developer.ninjatrader.com/docs/desktop/rendertarget\#definition)

A **SharpDX Direct2D1 RenderTarget** creates objects and exposes methods used for drawing in the chart area.

## Note

Notes:

1. There are two RenderTarget's used in a chart. This is important to understand when creating/destroying device resources. Please see the [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) page for more information.
2. For a walk through for using the SharpDX RenderTarget, please see the educational resource [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Property Value](https://developer.ninjatrader.com/docs/desktop/rendertarget\#property-value)

A [SharpDX.Direct2D1.RenderTarget](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget)

| Property | Description |
| --- | --- |
| **SharpDX.Direct2D1.WindowRenderTarget** | Used to render the actual contents of the chart to the window |
| **SharpDX.Direct2D1.WicRenderTarget** | Used to render a bitmap for a few scenarios:<br>1. A user clicks on a chart area; a bitmap is used to do any hit detection to determine where the user clicked.<br>2. User clicks on the Windows task bar; a bitmap is used to render the preview of the contents of the chart display through a thumbnail on the task bar.<br>3. A user re-sizes the chart; a bitmap is used to render the current contents of the chart, which is redrawn using the WindowRenderTarget after the desired changes have been set. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rendertarget\#syntax)

`RenderTarget`

## Warning

Warning: Each DirectX render target requires its own brushes. You must create brushes directly in [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) or using [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrestorevalues). If you do not, you will receive an error at run time similar to:

"A direct X error has occurred while rendering the chart: HRESULT: \[0x88990015\], Module: \[SharpDX.Direct2D1\], ApiCode: \[D2DERR\_WRONG\_RESOURCE\_DOMAIN/WrongResourceDomain\], Message: The resource was realized on the wrong render target. : Each DirectX render target requires its own brushes. You must create brushes directly in OnRender() or using OnRenderTargetChanged().

Please see [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) for examples with brushes that need to be recalculated, or [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) for an example of recreating a static brush.