Rendering methods and properties can be useful when carrying out custom drawing tasks for chart objects. Event handlers such as **OnCalculateMinMax()** and **OnRender()** allow you to override behavior at key points in the rendering process.

## Note

1. Some rendering methods and properties make use of [SharpDX](http://sharpdx.org/) libraries, which provide a managed framework for working with DirectX technology. Please see the [SharpDX SDK Reference](https://developer.ninjatrader.com/docs/desktop/sharpdx) for more information.
2. For a walk through for using the SharpDX, please see the educational resource [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/rendering\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) | Creates objects and exposes methods used for drawing in the chart area. |
| [ForceRefresh()](https://developer.ninjatrader.com/docs/desktop/forcerefresh) | Forces **OnRender()** to be called, which will re-paint the chart. |
| [IsInHitTest](https://developer.ninjatrader.com/docs/desktop/isinhittest) | Qualifies if object drawn in chart object should be selectable in the hit test procedure. |
| [IsSelected](https://developer.ninjatrader.com/docs/desktop/isselected) | Indicates a chart object is currently selected. |
| [IsVisibleOnChart()](https://developer.ninjatrader.com/docs/desktop/isvisibleonchart) | Indicates a chart object is visible on the chart canvas. |
| [MaxValue](https://developer.ninjatrader.com/docs/desktop/maxvalue) | The maximum value used for the automatic scaling of the y axis. |
| [MinValue](https://developer.ninjatrader.com/docs/desktop/minvalue) | The minimum value used for the automatic scaling of the y axis. |
| [OnCalculateMinMax()](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax) | An event driven method which is called while the chart scale is being updated. |
| [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) | Used to render custom drawing to a chart from various chart objects. |
| [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) | Used for efficient handling of SharpDX resources. |
| [PanelUI](https://developer.ninjatrader.com/docs/desktop/panelui) | The chart panel that is configured on the chart's UI. |
| [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) | A unique identifier used to control the order in which chart objects are drawn on the chart's Z-axis. |

Rendering methods and properties can be useful when carrying out custom drawing tasks for chart objects. Event handlers such as **OnCalculateMinMax()** and **OnRender()** allow you to override behavior at key points in the rendering process.

## Note

1. Some rendering methods and properties make use of [SharpDX](http://sharpdx.org/) libraries, which provide a managed framework for working with DirectX technology. Please see the [SharpDX SDK Reference](https://developer.ninjatrader.com/docs/desktop/sharpdx) for more information.
2. For a walk through for using the SharpDX, please see the educational resource [Using SharpDX for Custom Chart Rendering](https://developer.ninjatrader.com/docs/desktop/using_sharpdx_for_custom_chart_rendering).

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/rendering\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) | Creates objects and exposes methods used for drawing in the chart area. |
| [ForceRefresh()](https://developer.ninjatrader.com/docs/desktop/forcerefresh) | Forces **OnRender()** to be called, which will re-paint the chart. |
| [IsInHitTest](https://developer.ninjatrader.com/docs/desktop/isinhittest) | Qualifies if object drawn in chart object should be selectable in the hit test procedure. |
| [IsSelected](https://developer.ninjatrader.com/docs/desktop/isselected) | Indicates a chart object is currently selected. |
| [IsVisibleOnChart()](https://developer.ninjatrader.com/docs/desktop/isvisibleonchart) | Indicates a chart object is visible on the chart canvas. |
| [MaxValue](https://developer.ninjatrader.com/docs/desktop/maxvalue) | The maximum value used for the automatic scaling of the y axis. |
| [MinValue](https://developer.ninjatrader.com/docs/desktop/minvalue) | The minimum value used for the automatic scaling of the y axis. |
| [OnCalculateMinMax()](https://developer.ninjatrader.com/docs/desktop/oncalculateminmax) | An event driven method which is called while the chart scale is being updated. |
| [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) | Used to render custom drawing to a chart from various chart objects. |
| [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) | Used for efficient handling of SharpDX resources. |
| [PanelUI](https://developer.ninjatrader.com/docs/desktop/panelui) | The chart panel that is configured on the chart's UI. |
| [ZOrder](https://developer.ninjatrader.com/docs/desktop/chart_zorder) | A unique identifier used to control the order in which chart objects are drawn on the chart's Z-axis. |