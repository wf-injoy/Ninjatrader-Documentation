## [Definition](https://developer.ninjatrader.com/docs/desktop/chartanchor\#definition)

Defines objects used by Drawing Tools which represent a point on the chart where the Drawing Tool is located.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartanchor\#syntax)

`class ChartAnchor`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/chartanchor\#constructors)

| Constructor | Description |
| --- | --- |
| **new ChartAnchor()** | Initializes a new instance of the ChartAnchor object |
| **new ChartAnchor(DateTime time, double price, [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol))** | Initializes a new instance of the ChartAnchor object using time, price, and relative chart control |
| **new ChartAnchor(DateTime time, double yValue, int currentBar, [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol))** | Initializes a new instance of the ChartAnchor object using time, y-axis coordinates, current bar, and relative chart control |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartanchor\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| **[CopyDataValues()](https://developer.ninjatrader.com/docs/desktop/copydatavalues)** | Copies the ChartAnchor time and price values from one anchor to another |
| **[DisplayName](https://developer.ninjatrader.com/docs/desktop/displayname)** | A **string** value which sets the name prefix used for all properties for a chart anchor |
| **[DrawingTool](https://developer.ninjatrader.com/docs/desktop/drawingtool)** | The drawing tool which owns a chart anchor |
| **[DrawnOnBar](https://developer.ninjatrader.com/docs/desktop/drawnonbar)** | Gets the current bar value that the chart anchor is drawn by a NinjaScript object. |
| **[GetPoint()](https://developer.ninjatrader.com/docs/desktop/getpoint)** | Returns a chart anchor's data points. |
| **[IsBrowsable](https://developer.ninjatrader.com/docs/desktop/isbrowsable)** | A bool value determining if the anchor is visible on the UI. |
| **[IsEditing](https://developer.ninjatrader.com/docs/desktop/isediting)** | A bool value determining if the anchor is currently being edited |
| **[IsNinjaScriptDrawn](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn)** | Indicates if the chart anchor was drawn by a NinjaScript object |
| **[IsXPropertiesVisible](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile)** | A bool value determining if the X properties are visible on the UI |
| **[IsYPropertyVisible](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile)** | A bool value determining if the Y data value is visible on the UI |
| **[MoveAnchor()](https://developer.ninjatrader.com/docs/desktop/moveanchor)** | Moves a Chart Anchor's x and y values from start point by a delta point amount. |
| **[MoveAnchorX()](https://developer.ninjatrader.com/docs/desktop/moveanchorx)** | Moves an anchor's x values from start point by a delta point amount |
| **[MoveAnchorY()](https://developer.ninjatrader.com/docs/desktop/moveanchory)** | Moves an anchor's y values from start point by a delta point amount |
| **[Price](https://developer.ninjatrader.com/docs/desktop/price)** | Determines the price value the chart anchor is drawn. |
| **[SlotIndex](https://developer.ninjatrader.com/docs/desktop/barindex)** | Indicates the nearest bar slot where the anchor is drawn. |
| **[Time](https://developer.ninjatrader.com/docs/desktop/time)** | Determines the date/time value the chart anchor is drawn. |
| **[UpdateFromPoint()](https://developer.ninjatrader.com/docs/desktop/updatefrompoint)** | Updates an anchor's x and y values from a given point (in device pixels) |
| **[UpdateXFromPoint()](https://developer.ninjatrader.com/docs/desktop/updatexfrompoint)** | Updates an anchor's X values from a given point (in device pixels) |
| **[UpdateYFromPoint()](https://developer.ninjatrader.com/docs/desktop/updateyfrompoint)** | Updates an anchor's Y value from a given point (in device pixels) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartanchor\#examples)

```jsx-150469391 csharp

public ChartAnchor MyAnchor { get; set; } // declares the "MyAnchor" ChartAnchor object
public override IEnumerable<chartanchor> Anchors { get { return new[] { MyAnchor }; } } //adds the "MyAnchor" ChartAnchor object to a collection of anchors used to interact with your anchors
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Description = @"Drawing tool example";
     Name = "SampleDrawingTool";

     MyAnchor = new ChartAnchor(); //creates a new instance of the ChartAnchor object
     MyAnchor.IsEditing = true;
     MyAnchor.DrawingTool = this;
     MyAnchor.IsBrowsable = false;
   }
}

public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   if (DrawingState == DrawingState.Editing)
   {
     if (MyAnchor.IsEditing)
     {
         //if anchor is editing, update anchor point
         dataPoint.CopyDataValues(MyAnchor);
     }
   }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartanchor\#definition)

Defines objects used by Drawing Tools which represent a point on the chart where the Drawing Tool is located.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartanchor\#syntax)

`class ChartAnchor`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/chartanchor\#constructors)

| Constructor | Description |
| --- | --- |
| **new ChartAnchor()** | Initializes a new instance of the ChartAnchor object |
| **new ChartAnchor(DateTime time, double price, [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol))** | Initializes a new instance of the ChartAnchor object using time, price, and relative chart control |
| **new ChartAnchor(DateTime time, double yValue, int currentBar, [ChartControl](https://developer.ninjatrader.com/docs/desktop/chartcontrol))** | Initializes a new instance of the ChartAnchor object using time, y-axis coordinates, current bar, and relative chart control |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/chartanchor\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| **[CopyDataValues()](https://developer.ninjatrader.com/docs/desktop/copydatavalues)** | Copies the ChartAnchor time and price values from one anchor to another |
| **[DisplayName](https://developer.ninjatrader.com/docs/desktop/displayname)** | A **string** value which sets the name prefix used for all properties for a chart anchor |
| **[DrawingTool](https://developer.ninjatrader.com/docs/desktop/drawingtool)** | The drawing tool which owns a chart anchor |
| **[DrawnOnBar](https://developer.ninjatrader.com/docs/desktop/drawnonbar)** | Gets the current bar value that the chart anchor is drawn by a NinjaScript object. |
| **[GetPoint()](https://developer.ninjatrader.com/docs/desktop/getpoint)** | Returns a chart anchor's data points. |
| **[IsBrowsable](https://developer.ninjatrader.com/docs/desktop/isbrowsable)** | A bool value determining if the anchor is visible on the UI. |
| **[IsEditing](https://developer.ninjatrader.com/docs/desktop/isediting)** | A bool value determining if the anchor is currently being edited |
| **[IsNinjaScriptDrawn](https://developer.ninjatrader.com/docs/desktop/isninjascriptdrawn)** | Indicates if the chart anchor was drawn by a NinjaScript object |
| **[IsXPropertiesVisible](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile)** | A bool value determining if the X properties are visible on the UI |
| **[IsYPropertyVisible](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile)** | A bool value determining if the Y data value is visible on the UI |
| **[MoveAnchor()](https://developer.ninjatrader.com/docs/desktop/moveanchor)** | Moves a Chart Anchor's x and y values from start point by a delta point amount. |
| **[MoveAnchorX()](https://developer.ninjatrader.com/docs/desktop/moveanchorx)** | Moves an anchor's x values from start point by a delta point amount |
| **[MoveAnchorY()](https://developer.ninjatrader.com/docs/desktop/moveanchory)** | Moves an anchor's y values from start point by a delta point amount |
| **[Price](https://developer.ninjatrader.com/docs/desktop/price)** | Determines the price value the chart anchor is drawn. |
| **[SlotIndex](https://developer.ninjatrader.com/docs/desktop/barindex)** | Indicates the nearest bar slot where the anchor is drawn. |
| **[Time](https://developer.ninjatrader.com/docs/desktop/time)** | Determines the date/time value the chart anchor is drawn. |
| **[UpdateFromPoint()](https://developer.ninjatrader.com/docs/desktop/updatefrompoint)** | Updates an anchor's x and y values from a given point (in device pixels) |
| **[UpdateXFromPoint()](https://developer.ninjatrader.com/docs/desktop/updatexfrompoint)** | Updates an anchor's X values from a given point (in device pixels) |
| **[UpdateYFromPoint()](https://developer.ninjatrader.com/docs/desktop/updateyfrompoint)** | Updates an anchor's Y value from a given point (in device pixels) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartanchor\#examples)

```jsx-150469391 csharp

public ChartAnchor MyAnchor { get; set; } // declares the "MyAnchor" ChartAnchor object
public override IEnumerable<chartanchor> Anchors { get { return new[] { MyAnchor }; } } //adds the "MyAnchor" ChartAnchor object to a collection of anchors used to interact with your anchors
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Description = @"Drawing tool example";
     Name = "SampleDrawingTool";

     MyAnchor = new ChartAnchor(); //creates a new instance of the ChartAnchor object
     MyAnchor.IsEditing = true;
     MyAnchor.DrawingTool = this;
     MyAnchor.IsBrowsable = false;
   }
}

public override void OnMouseUp(ChartControl chartControl, ChartPanel chartPanel, ChartScale chartScale, ChartAnchor dataPoint)
{
   if (DrawingState == DrawingState.Editing)
   {
     if (MyAnchor.IsEditing)
     {
         //if anchor is editing, update anchor point
         dataPoint.CopyDataValues(MyAnchor);
     }
   }

```