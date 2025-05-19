The **ChartControl** class provides access to a wide range of properties and methods related to the location of objects on a chart and other chart-related properties. The **ChartControl** object provides information related to the entire hosting grid of the chart, which overlap with the [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel), [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) and [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars).

## Note

The **ChartControl** object is ONLY guaranteed to be available when a **NinjaScript** type initiates from a Chart Window. There are situations where an indicator or strategy starts from another Windows (such as the Control Center's Strategies Grid, or from a Strategy Analyzer), where the **ChartControl** object is NOT accessible. Therefore, the **ChartControl** object should always be safely accessed (e.g., from within a try-catch, or conditionally using null reference checks).

## Warning

Warning: The **ChartControl** and its methods and properties should ONLY be accessed once the **State** has reached **State.Historical**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartcontrol\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AxisXHeight](https://developer.ninjatrader.com/docs/desktop/axisxheight) | Measures the distance (in pixels) between the x-axis and the top of the horizontal scroll bar |
| [AxisYLeftWidth](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth) | Measures the distance (in pixels) between the y-axis and the left margin of a chart |
| [AxisYRightWidth](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth) | Measures the distance (in pixels) between the y-axis and the right margin of a chart |
| [BarMarginLeft](https://developer.ninjatrader.com/docs/desktop/barmarginleft) | Measures the margin to the left of each bar on the chart, in pixels |
| [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) | Provides a collection of [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) objects currently configured on the chart |
| [BarSpacingType](https://developer.ninjatrader.com/docs/desktop/barspacingtype) | Provides the type of bar spacing used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barsperiod) | Provides the period (interval) used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarWidth](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth) | Measures the value of the bar width set for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarWidthArray](https://developer.ninjatrader.com/docs/desktop/barwidtharray) | An array containing the values of the [BarWidth](https://developer.ninjatrader.com/docs/desktop/barwidth) properties of all [Bars](https://developer.ninjatrader.com/docs/desktop/bars) objects on the chart |
| [CanvasLeft](https://developer.ninjatrader.com/docs/desktop/canvasleft) | Indicates the x-coordinate (in pixels) of the beginning of the chart canvas area |
| [CanvasRight](https://developer.ninjatrader.com/docs/desktop/canvasright) | Indicates the x-coordinate (in pixels) of the end of the chart canvas area |
| [CanvasZoomState](https://developer.ninjatrader.com/docs/desktop/canvaszoomstate) | Indicates the current state of the Zoom tool on the chart |
| [ChartPanels](https://developer.ninjatrader.com/docs/desktop/chartpanels) | Holds a collection of [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) objects |
| [CrosshairType](https://developer.ninjatrader.com/docs/desktop/crosshairtype) | Indicates the [Cross Hair](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?cross_hair.htm) type currently enabled on the chart |
| [FirstTimePainted](https://developer.ninjatrader.com/docs/desktop/firsttimepainted) | Indicates a time value of the first bar painted on the chart |
| [GetBarPaintWidth()](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth) | Returns the width of the bars in the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart, in pixels |
| [GetSlotIndexByTime()](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime) | Returns the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart corresponding to a specified time value |
| [GetSlotIndexByX()](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx) | Returns the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart corresponding to a specified x-coordinate on the visible chart canvas |
| [GetTimeBySlotIndex()](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex) | Returns a time value corresponding to a specified slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [GetTimeByX()](https://developer.ninjatrader.com/docs/desktop/gettimebyx) | Returns a time value related to the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars)' slot index at a specified x-coordinate on the chart canvas |
| [GetXByBarIndex()](https://developer.ninjatrader.com/docs/desktop/getxbybarindex) | Returns the chart-canvas x-coordinate of the bar at a specified index of a specified [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) object on the chart |
| [GetXByTime()](https://developer.ninjatrader.com/docs/desktop/getxbytime) | Returns the chart-canvas x-coordinate of the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object corresponding to a specified time |
| [Indicators](https://developer.ninjatrader.com/docs/desktop/indicators) | Returns a collection of indicators currently configured on the chart |
| [IsScrollArrowVisible](https://developer.ninjatrader.com/docs/desktop/isscrollarrowvisible) | Indicates the time-axis scroll arrow is visible in the top-right corner of the chart |
| [IsStayInDrawMode](https://developer.ninjatrader.com/docs/desktop/isstayindrawmode) | Indicates the [Stay in Draw Mode](https://ninjatrader.com/support/helpGuides/nt8/?working_with_drawing_tools__ob.htm) is currently enabled on the chart |
| [IsYAxisDisplayedLeft](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedleft) | Indicates the y-axis displays (in any chart panel) to the left side of the chart canvas |
| [IsYAxisDisplayedOverlay](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay) | Indicates an object on the chart is using the Overlay scale justification |
| [IsYAxisDisplayedRight](https://developer.ninjatrader.com/docs/desktop/chartcontrol_isyaxisdisplayedright) | Indicates the y-axis displays (in any chart panel) to the right side of the chart canvas |
| [LastSlotPainted](https://developer.ninjatrader.com/docs/desktop/lastslotpainted) | Indicates the slot index of the most recently painted bar on the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object configured on the chart |
| [LastTimePainted](https://developer.ninjatrader.com/docs/desktop/lasttimepainted) | Indicates the time of the most recently painted bar on the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object configured on the chart |
| [MouseDownPoint](https://developer.ninjatrader.com/docs/desktop/mousedownpoint) | Indicates the x- and y-coordinates of the mouse cursor at the most recent **OnMouseDown()** event |
| [Properties](https://developer.ninjatrader.com/docs/desktop/chartcontrol_properties) | A collection of properties related to the configuration of the Chart |
| [SlotsPainted](https://developer.ninjatrader.com/docs/desktop/slotspainted) | Indicates the number of index slots in which bars are painted within the chart canvas area |
| [Strategies](https://developer.ninjatrader.com/docs/desktop/strategies) | A collection of strategies configured on the chart |
| [TimePainted](https://developer.ninjatrader.com/docs/desktop/timepainted) | Indicates the range of time in which bars are painted on the visible chart canvas |

The **ChartControl** class provides access to a wide range of properties and methods related to the location of objects on a chart and other chart-related properties. The **ChartControl** object provides information related to the entire hosting grid of the chart, which overlap with the [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel), [ChartScale](https://developer.ninjatrader.com/docs/desktop/chartscale) and [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars).

## Note

The **ChartControl** object is ONLY guaranteed to be available when a **NinjaScript** type initiates from a Chart Window. There are situations where an indicator or strategy starts from another Windows (such as the Control Center's Strategies Grid, or from a Strategy Analyzer), where the **ChartControl** object is NOT accessible. Therefore, the **ChartControl** object should always be safely accessed (e.g., from within a try-catch, or conditionally using null reference checks).

## Warning

Warning: The **ChartControl** and its methods and properties should ONLY be accessed once the **State** has reached **State.Historical**.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartcontrol\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [AxisXHeight](https://developer.ninjatrader.com/docs/desktop/axisxheight) | Measures the distance (in pixels) between the x-axis and the top of the horizontal scroll bar |
| [AxisYLeftWidth](https://developer.ninjatrader.com/docs/desktop/axisyleftwidth) | Measures the distance (in pixels) between the y-axis and the left margin of a chart |
| [AxisYRightWidth](https://developer.ninjatrader.com/docs/desktop/axisyrightwidth) | Measures the distance (in pixels) between the y-axis and the right margin of a chart |
| [BarMarginLeft](https://developer.ninjatrader.com/docs/desktop/barmarginleft) | Measures the margin to the left of each bar on the chart, in pixels |
| [BarsArray](https://developer.ninjatrader.com/docs/desktop/barsarray) | Provides a collection of [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) objects currently configured on the chart |
| [BarSpacingType](https://developer.ninjatrader.com/docs/desktop/barspacingtype) | Provides the type of bar spacing used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barsperiod) | Provides the period (interval) used for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarWidth](https://developer.ninjatrader.com/docs/desktop/chartcontrol_barwidth) | Measures the value of the bar width set for the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [BarWidthArray](https://developer.ninjatrader.com/docs/desktop/barwidtharray) | An array containing the values of the [BarWidth](https://developer.ninjatrader.com/docs/desktop/barwidth) properties of all [Bars](https://developer.ninjatrader.com/docs/desktop/bars) objects on the chart |
| [CanvasLeft](https://developer.ninjatrader.com/docs/desktop/canvasleft) | Indicates the x-coordinate (in pixels) of the beginning of the chart canvas area |
| [CanvasRight](https://developer.ninjatrader.com/docs/desktop/canvasright) | Indicates the x-coordinate (in pixels) of the end of the chart canvas area |
| [CanvasZoomState](https://developer.ninjatrader.com/docs/desktop/canvaszoomstate) | Indicates the current state of the Zoom tool on the chart |
| [ChartPanels](https://developer.ninjatrader.com/docs/desktop/chartpanels) | Holds a collection of [ChartPanel](https://developer.ninjatrader.com/docs/desktop/chartpanel) objects |
| [CrosshairType](https://developer.ninjatrader.com/docs/desktop/crosshairtype) | Indicates the [Cross Hair](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?cross_hair.htm) type currently enabled on the chart |
| [FirstTimePainted](https://developer.ninjatrader.com/docs/desktop/firsttimepainted) | Indicates a time value of the first bar painted on the chart |
| [GetBarPaintWidth()](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth) | Returns the width of the bars in the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart, in pixels |
| [GetSlotIndexByTime()](https://developer.ninjatrader.com/docs/desktop/getslotindexbytime) | Returns the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart corresponding to a specified time value |
| [GetSlotIndexByX()](https://developer.ninjatrader.com/docs/desktop/getslotindexbyx) | Returns the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart corresponding to a specified x-coordinate on the visible chart canvas |
| [GetTimeBySlotIndex()](https://developer.ninjatrader.com/docs/desktop/gettimebyslotindex) | Returns a time value corresponding to a specified slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object on the chart |
| [GetTimeByX()](https://developer.ninjatrader.com/docs/desktop/gettimebyx) | Returns a time value related to the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars)' slot index at a specified x-coordinate on the chart canvas |
| [GetXByBarIndex()](https://developer.ninjatrader.com/docs/desktop/getxbybarindex) | Returns the chart-canvas x-coordinate of the bar at a specified index of a specified [ChartBars](https://developer.ninjatrader.com/docs/desktop/chartbars) object on the chart |
| [GetXByTime()](https://developer.ninjatrader.com/docs/desktop/getxbytime) | Returns the chart-canvas x-coordinate of the slot index of the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object corresponding to a specified time |
| [Indicators](https://developer.ninjatrader.com/docs/desktop/indicators) | Returns a collection of indicators currently configured on the chart |
| [IsScrollArrowVisible](https://developer.ninjatrader.com/docs/desktop/isscrollarrowvisible) | Indicates the time-axis scroll arrow is visible in the top-right corner of the chart |
| [IsStayInDrawMode](https://developer.ninjatrader.com/docs/desktop/isstayindrawmode) | Indicates the [Stay in Draw Mode](https://ninjatrader.com/support/helpGuides/nt8/?working_with_drawing_tools__ob.htm) is currently enabled on the chart |
| [IsYAxisDisplayedLeft](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedleft) | Indicates the y-axis displays (in any chart panel) to the left side of the chart canvas |
| [IsYAxisDisplayedOverlay](https://developer.ninjatrader.com/docs/desktop/isyaxisdisplayedoverlay) | Indicates an object on the chart is using the Overlay scale justification |
| [IsYAxisDisplayedRight](https://developer.ninjatrader.com/docs/desktop/chartcontrol_isyaxisdisplayedright) | Indicates the y-axis displays (in any chart panel) to the right side of the chart canvas |
| [LastSlotPainted](https://developer.ninjatrader.com/docs/desktop/lastslotpainted) | Indicates the slot index of the most recently painted bar on the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object configured on the chart |
| [LastTimePainted](https://developer.ninjatrader.com/docs/desktop/lasttimepainted) | Indicates the time of the most recently painted bar on the primary [Bars](https://developer.ninjatrader.com/docs/desktop/bars) object configured on the chart |
| [MouseDownPoint](https://developer.ninjatrader.com/docs/desktop/mousedownpoint) | Indicates the x- and y-coordinates of the mouse cursor at the most recent **OnMouseDown()** event |
| [Properties](https://developer.ninjatrader.com/docs/desktop/chartcontrol_properties) | A collection of properties related to the configuration of the Chart |
| [SlotsPainted](https://developer.ninjatrader.com/docs/desktop/slotspainted) | Indicates the number of index slots in which bars are painted within the chart canvas area |
| [Strategies](https://developer.ninjatrader.com/docs/desktop/strategies) | A collection of strategies configured on the chart |
| [TimePainted](https://developer.ninjatrader.com/docs/desktop/timepainted) | Indicates the range of time in which bars are painted on the visible chart canvas |