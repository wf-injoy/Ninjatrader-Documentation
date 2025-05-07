## [Definition](https://developer.ninjatrader.com/docs/desktop/anchors\#definition)

Returns a custom collection of ChartAnchors which will represent various points of the drawing tool.

## Note

You must declare this property with the chart anchors used in the drawing tool which you plan on using for iteration. Doing so will expose a simple enumerator which will allow you to to iterate over the chart anchors in which have been defined in this interface.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/anchors\#property-value)

A virtual **IEnumerable** interface consisting of **ChartAnchors**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/anchors\#syntax)

You must override this property using the following syntax:

`public override IEnumerable<chartanchor> Anchors { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/anchors\#examples)

```jsx-150469391 csharp
//defines the chart anchors used for the drawing tool
public ChartAnchor StartAnchor { get; set; }
public ChartAnchor MiddleAnchor { get; set; }
public ChartAnchor EndAnchor { get; set; }

//create a collection of chart anchors used for a simple iteration
public override IEnumerable<chartanchor> Anchors
{
   get
   {
     return new[] { StartAnchor, MiddleAnchor, EndAnchor };
   }
}

//setup our chart anchor instances and assign a display name to each
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      Name = "My Drawing Tool";

      StartAnchor = new ChartAnchor();
      MiddleAnchor = new ChartAnchor();
      EndAnchor = new ChartAnchor();

      StartAnchor.DisplayName = "My Start Anchor";
      MiddleAnchor.DisplayName = "My Middle Anchor";
      EndAnchor.DisplayName = "My End Anchor";
   }
}

//for each render pass, print out the display name of the chart anchors
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   foreach (ChartAnchor anchor in Anchors)
   {
      Print(anchor.DisplayName);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/anchors\#definition)

Returns a custom collection of ChartAnchors which will represent various points of the drawing tool.

## Note

You must declare this property with the chart anchors used in the drawing tool which you plan on using for iteration. Doing so will expose a simple enumerator which will allow you to to iterate over the chart anchors in which have been defined in this interface.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/anchors\#property-value)

A virtual **IEnumerable** interface consisting of **ChartAnchors**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/anchors\#syntax)

You must override this property using the following syntax:

`public override IEnumerable<chartanchor> Anchors { }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/anchors\#examples)

```jsx-150469391 csharp
//defines the chart anchors used for the drawing tool
public ChartAnchor StartAnchor { get; set; }
public ChartAnchor MiddleAnchor { get; set; }
public ChartAnchor EndAnchor { get; set; }

//create a collection of chart anchors used for a simple iteration
public override IEnumerable<chartanchor> Anchors
{
   get
   {
     return new[] { StartAnchor, MiddleAnchor, EndAnchor };
   }
}

//setup our chart anchor instances and assign a display name to each
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      Name = "My Drawing Tool";

      StartAnchor = new ChartAnchor();
      MiddleAnchor = new ChartAnchor();
      EndAnchor = new ChartAnchor();

      StartAnchor.DisplayName = "My Start Anchor";
      MiddleAnchor.DisplayName = "My Middle Anchor";
      EndAnchor.DisplayName = "My End Anchor";
   }
}

//for each render pass, print out the display name of the chart anchors
protected override void OnRender(ChartControl chartControl, ChartScale chartScale)
{
   foreach (ChartAnchor anchor in Anchors)
   {
      Print(anchor.DisplayName);
   }
}

```