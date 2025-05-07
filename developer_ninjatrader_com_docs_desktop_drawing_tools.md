Custom Drawing Tools can be used to render custom shapes to a point on the chart to represent various information. The methods and properties covered in this section are unique to custom Drawing Tools development. Following is an index of the documented properties and methods related to drawing tools.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/drawing_tools\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AddPastedOffset()](https://developer.ninjatrader.com/docs/desktop/addpastedoffset) | A **virtual method** which is called every time a Drawing Tool is copied and pasted to a chart |
| [Anchors](https://developer.ninjatrader.com/docs/desktop/anchors) | Creates a collection of Chart Anchors which will represent various points of the drawing tool |
| [AttachedTo](https://developer.ninjatrader.com/docs/desktop/attachedto) | An object which holds information regarding where the drawing tool is attached |
| [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) | Defines objects used by Drawing Tools which represent a point on the chart where the Drawing Tool is located |
| [ConvertToVerticalPixels](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels) | Used to convert the cursor position (pixels) to device pixels represented on the Y axis of the chart |
| [CreateAnchor()](https://developer.ninjatrader.com/docs/desktop/createanchor) | Used to create a new chart anchor at a specified mouse point |
| [DisplayOnChartsMenus](https://developer.ninjatrader.com/docs/desktop/displayonchartsmenus) | Determines if the drawing tool should be listed in the chart's drawing tool menus |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/dispose) | Releases any device resources used for the drawing tool |
| [DrawingState](https://developer.ninjatrader.com/docs/desktop/drawingstate) | Represents the current state of the drawing tool in order to perform various actions, such as building, editing, or moving |
| [DrawnBy](https://developer.ninjatrader.com/docs/desktop/drawnby) | Represents the NinjaScript object by which the drawing tool was created |
| [GetAttachedToChartBars()](https://developer.ninjatrader.com/docs/desktop/getattachedtochartbars) | Returns information which relate to the underlying bars series in which the drawing tool is attached |
| [GetClosestAnchor()](https://developer.ninjatrader.com/docs/desktop/getclosestanchor) | Returns the closest chart anchor within a specified maximum distance from the mouse cursor |
| [GetCursor()](https://developer.ninjatrader.com/docs/desktop/getcursor) | An event driven method which is called when a chart object is selected |
| [GetSelectionPoints()](https://developer.ninjatrader.com/docs/desktop/getselectionpoints) | Returns the chart object's data points where the user can interact |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon_drawingtool) | The shape which displays next to the drawing tool menu item |
| [IgnoresSnapping](https://developer.ninjatrader.com/docs/desktop/ignoresnapping) | Determines if the drawing tool chart anchor's will use the chart's Snap Mode mouse coordinates |
| [IgnoresUserInput](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput) | Determines if the drawing tool can be clicked on by the user |
| [IsAttachedToNinjaScript](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript) | Indicates if the drawing tool is currently **attached to** a NinjaScript object (such an indicator or a strategy) |
| [IsGlobalDrawingTool](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool) | Indicates if the drawing tool is currently set as a Global Drawing object |
| [IsLocked](https://developer.ninjatrader.com/docs/desktop/islocked) | Determines if the drawing tool should be locked in place |
| [IsUserDrawn](https://developer.ninjatrader.com/docs/desktop/isuserdrawn) | Indicates if the drawing tool was manually drawn by a user |
| [OnBarsChanged()](https://developer.ninjatrader.com/docs/desktop/onbarschanged) | An event driven method which is called any time the underlying bar series have changed for the chart where the drawing tool resides |
| [OnMouseDown()](https://developer.ninjatrader.com/docs/desktop/onmousedown) | An event driven method which is called any time the mouse pointer over the chart control has the mouse button pressed |
| [OnMouseMove()](https://developer.ninjatrader.com/docs/desktop/onmousemove) | An event driven method which is called any time the mouse pointer is over the chart control and a mouse is moving |
| [OnMouseUp()](https://developer.ninjatrader.com/docs/desktop/onmouseup) | An event driven method is called any time the mouse pointer is over the chart control and a mouse button is being released |
| [SupportsAlerts](https://developer.ninjatrader.com/docs/desktop/supportsalerts) | Indicates if the drawing tool can be used for manually configured alerts through the UI |
| [ZOrderType](https://developer.ninjatrader.com/docs/desktop/zordertype) | Determines the order in which the drawing tool will be rendered |

Custom Drawing Tools can be used to render custom shapes to a point on the chart to represent various information. The methods and properties covered in this section are unique to custom Drawing Tools development. Following is an index of the documented properties and methods related to drawing tools.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/drawing_tools\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AddPastedOffset()](https://developer.ninjatrader.com/docs/desktop/addpastedoffset) | A **virtual method** which is called every time a Drawing Tool is copied and pasted to a chart |
| [Anchors](https://developer.ninjatrader.com/docs/desktop/anchors) | Creates a collection of Chart Anchors which will represent various points of the drawing tool |
| [AttachedTo](https://developer.ninjatrader.com/docs/desktop/attachedto) | An object which holds information regarding where the drawing tool is attached |
| [ChartAnchor](https://developer.ninjatrader.com/docs/desktop/chartanchor) | Defines objects used by Drawing Tools which represent a point on the chart where the Drawing Tool is located |
| [ConvertToVerticalPixels](https://developer.ninjatrader.com/docs/desktop/converttoverticalpixels) | Used to convert the cursor position (pixels) to device pixels represented on the Y axis of the chart |
| [CreateAnchor()](https://developer.ninjatrader.com/docs/desktop/createanchor) | Used to create a new chart anchor at a specified mouse point |
| [DisplayOnChartsMenus](https://developer.ninjatrader.com/docs/desktop/displayonchartsmenus) | Determines if the drawing tool should be listed in the chart's drawing tool menus |
| [Dispose()](https://developer.ninjatrader.com/docs/desktop/dispose) | Releases any device resources used for the drawing tool |
| [DrawingState](https://developer.ninjatrader.com/docs/desktop/drawingstate) | Represents the current state of the drawing tool in order to perform various actions, such as building, editing, or moving |
| [DrawnBy](https://developer.ninjatrader.com/docs/desktop/drawnby) | Represents the NinjaScript object by which the drawing tool was created |
| [GetAttachedToChartBars()](https://developer.ninjatrader.com/docs/desktop/getattachedtochartbars) | Returns information which relate to the underlying bars series in which the drawing tool is attached |
| [GetClosestAnchor()](https://developer.ninjatrader.com/docs/desktop/getclosestanchor) | Returns the closest chart anchor within a specified maximum distance from the mouse cursor |
| [GetCursor()](https://developer.ninjatrader.com/docs/desktop/getcursor) | An event driven method which is called when a chart object is selected |
| [GetSelectionPoints()](https://developer.ninjatrader.com/docs/desktop/getselectionpoints) | Returns the chart object's data points where the user can interact |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon_drawingtool) | The shape which displays next to the drawing tool menu item |
| [IgnoresSnapping](https://developer.ninjatrader.com/docs/desktop/ignoresnapping) | Determines if the drawing tool chart anchor's will use the chart's Snap Mode mouse coordinates |
| [IgnoresUserInput](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput) | Determines if the drawing tool can be clicked on by the user |
| [IsAttachedToNinjaScript](https://developer.ninjatrader.com/docs/desktop/isattachedtoninjascript) | Indicates if the drawing tool is currently **attached to** a NinjaScript object (such an indicator or a strategy) |
| [IsGlobalDrawingTool](https://developer.ninjatrader.com/docs/desktop/isglobaldrawingtool) | Indicates if the drawing tool is currently set as a Global Drawing object |
| [IsLocked](https://developer.ninjatrader.com/docs/desktop/islocked) | Determines if the drawing tool should be locked in place |
| [IsUserDrawn](https://developer.ninjatrader.com/docs/desktop/isuserdrawn) | Indicates if the drawing tool was manually drawn by a user |
| [OnBarsChanged()](https://developer.ninjatrader.com/docs/desktop/onbarschanged) | An event driven method which is called any time the underlying bar series have changed for the chart where the drawing tool resides |
| [OnMouseDown()](https://developer.ninjatrader.com/docs/desktop/onmousedown) | An event driven method which is called any time the mouse pointer over the chart control has the mouse button pressed |
| [OnMouseMove()](https://developer.ninjatrader.com/docs/desktop/onmousemove) | An event driven method which is called any time the mouse pointer is over the chart control and a mouse is moving |
| [OnMouseUp()](https://developer.ninjatrader.com/docs/desktop/onmouseup) | An event driven method is called any time the mouse pointer is over the chart control and a mouse button is being released |
| [SupportsAlerts](https://developer.ninjatrader.com/docs/desktop/supportsalerts) | Indicates if the drawing tool can be used for manually configured alerts through the UI |
| [ZOrderType](https://developer.ninjatrader.com/docs/desktop/zordertype) | Determines the order in which the drawing tool will be rendered |