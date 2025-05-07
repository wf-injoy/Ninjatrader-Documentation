## [Definition](https://developer.ninjatrader.com/docs/desktop/addplot\#definition)

Adds plot objects that define how an indicator or strategy data series render on a chart. When this method is called to add a plot, an associated **Series< `double` >** object is created held in the **Values** collection.

## Note

Plots are ONLY visible from the UI property grid when AddPlot() is called from State.SetDefaults. If your indicator or strategy dynamically adds plots during State.Configure, you will NOT have an opportunity to select the plot or to set the plot configuration via the UI. Alternatively, you may use custom public **Brush**, **Stroke**, or PlotStyle properties which are accessible in State.SetDefaults and pass those values to AddPlot() during State.Configure. Calling AddPlot() in this manner should be reserved for special cases. Please see the examples below.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/addplot\#methods-and-properties)

| [ArePlotsConfigurable](https://developer.ninjatrader.com/docs/desktop/areplotsconfigurable) | Determines if the plot(s) used in an indicator are configurable within the indicator dialog window. |
| [Displacement](https://developer.ninjatrader.com/docs/desktop/displacement) | An offset value that shifts the visually displayed value of an indicator. |
| [PlotBrushes](https://developer.ninjatrader.com/docs/desktop/plotbrushes) | Holds an array of color series objects holding historical bar colors. |
| [Plots](https://developer.ninjatrader.com/docs/desktop/plots) | A collection holding all of the Plot objects that define their visualization characteristics. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addplot\#syntax)

`AddPlot(Brush brush, string name)`

`AddPlot(Stroke stroke, PlotStyle plotStyle, string name)`

## Warning

This method should ONLY be called within the `OnStateChange()` method during **State.SetDefaults** or **State.Configure**

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addplot\#parameters)

| brush | A Brush object used to construct the plot |
| name | A string representing the name of the plot |
| plotStyle | A PlotStyle object used to construct the style of the plot. Possible values:<br>- PlotStyle.Bar<br>- PlotStyle.Block<br>- PlotStyle.Cross<br>- PlotStyle.Dot<br>- PlotStyle.Hash<br>- PlotStyle.HLine<br>- PlotStyle.Line<br>- PlotStyle.PriceBox<br>- PlotStyle.Square<br>- PlotStyle.TriangleDown<br>- PlotStyle.TriangleLeft<br>- PlotStyle.TriangleRight<br>- PlotStyle.TriangleUp |
| stroke | A Stroke object used to construct the plot |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addplot\#examples)

### Indicator using various AddPlot() signatures

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";

     // Adds a blue line style plot
     AddPlot(Brushes.Blue, "MyPlot");

     // Adds a blue historgram style plot
     AddPlot(new Stroke(Brushes.Blue), PlotStyle.Bar, "MyPlot2");

     // Ensures that the width of the PlotStyle.Bar plot matches the width of the data series
     Plots[1].AutoWidth = true;

      // Adds a blue Dash-Line style plot with 5pixel width and 50% opacity
     AddPlot(new Stroke(Brushes.Blue, DashStyleHelper.Dash, 5, 50), PlotStyle.Line, "MyPlot3");
   }
}

```

### Indicator using a public `Series<double>` to expose a plot with a friendly name

## Note

This is required for making plots accessible in the strategy builder. For an example on exposing other variables publicly, see [exposing indicator values that are not plots](https://developer.ninjatrader.com/docs/desktop/exposing_indicator_values_that_are_not_plots)

```jsx-150469391 csharp
protected override void OnStateChange()

{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
     // Adds a blue line style plot
     AddPlot(Brushes.Blue, "MyPlot");
     // Adds a blue historgram style plot
     AddPlot(new Stroke(Brushes.Blue), PlotStyle.Bar, "MyPlot2");
   }
}
protected override void OnBarUpdate()
{
   MyPlot[0] = Close[0] + High[0] / 2​;
   MyPlot[1] = Close[0] + High[0] / 2​;
}
[Browsable(false)]
[XmlIgnore]
public Series<double> MyPlot
{
   get { return Values[0]; }
}
[Browsable(false)]
[XmlIgnore]
public Series<double> MyPlot2
{
   get { return Values[1]; }
}

```

### Indicator which adds three value series

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
     // Add three plots and associated Series<double> objects
     AddPlot(Brushes.Blue, "PlotA");     // Defines the plot for Values[0]
     AddPlot(Brushes.Red, "PlotB");     // Defines the plot for Values[1]
     AddPlot(Brushes.Green, "PlotC");   // Defines the plot for Values[2]
   }
}
protected override void OnBarUpdate()
{
   Values[0][0] = Median[0];   // Blue "Plot A"
   Values[1][0] = Low[0];       // Red "Plot B"
   Values[2][0] = High[0];     // Green "Plot C"
}

```

### Indicator which dynamically adds a plot in state.configure

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name                 = "Examples Indicator";
     // logical property which user can set
     UseSpecialMode   = false;
     // Default brush selection pushed to the UI
     MyBrush = Brushes.Red;
   }
   else if (State == State.Configure)
   {
     // if user enables logical property
     if (UseSpecialMode)
     {
         // add plot using default selected brush and special plot name
         AddPlot(MyBrush, "My Special Plot");
     }
     else
     {
         // otherwise use default selected brush and regular plot name
         AddPlot(MyBrush, "My Regular Plot");
     }
   }
}
protected override void OnBarUpdate()
{
   if (UseSpecialMode)
     Value[0] = Close[0] + High[0] / 2;
   else Value[0] = Close[0] * TickSize / 2;
}
[XmlIgnore]
public Brush MyBrush { get; set; }
public bool UseSpecialMode { get; set; }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/addplot\#definition)

Adds plot objects that define how an indicator or strategy data series render on a chart. When this method is called to add a plot, an associated **Series< `double` >** object is created held in the **Values** collection.

## Note

Plots are ONLY visible from the UI property grid when AddPlot() is called from State.SetDefaults. If your indicator or strategy dynamically adds plots during State.Configure, you will NOT have an opportunity to select the plot or to set the plot configuration via the UI. Alternatively, you may use custom public **Brush**, **Stroke**, or PlotStyle properties which are accessible in State.SetDefaults and pass those values to AddPlot() during State.Configure. Calling AddPlot() in this manner should be reserved for special cases. Please see the examples below.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/addplot\#methods-and-properties)

| [ArePlotsConfigurable](https://developer.ninjatrader.com/docs/desktop/areplotsconfigurable) | Determines if the plot(s) used in an indicator are configurable within the indicator dialog window. |
| [Displacement](https://developer.ninjatrader.com/docs/desktop/displacement) | An offset value that shifts the visually displayed value of an indicator. |
| [PlotBrushes](https://developer.ninjatrader.com/docs/desktop/plotbrushes) | Holds an array of color series objects holding historical bar colors. |
| [Plots](https://developer.ninjatrader.com/docs/desktop/plots) | A collection holding all of the Plot objects that define their visualization characteristics. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/addplot\#syntax)

`AddPlot(Brush brush, string name)`

`AddPlot(Stroke stroke, PlotStyle plotStyle, string name)`

## Warning

This method should ONLY be called within the `OnStateChange()` method during **State.SetDefaults** or **State.Configure**

## [Parameters](https://developer.ninjatrader.com/docs/desktop/addplot\#parameters)

| brush | A Brush object used to construct the plot |
| name | A string representing the name of the plot |
| plotStyle | A PlotStyle object used to construct the style of the plot. Possible values:<br>- PlotStyle.Bar<br>- PlotStyle.Block<br>- PlotStyle.Cross<br>- PlotStyle.Dot<br>- PlotStyle.Hash<br>- PlotStyle.HLine<br>- PlotStyle.Line<br>- PlotStyle.PriceBox<br>- PlotStyle.Square<br>- PlotStyle.TriangleDown<br>- PlotStyle.TriangleLeft<br>- PlotStyle.TriangleRight<br>- PlotStyle.TriangleUp |
| stroke | A Stroke object used to construct the plot |

## [Examples](https://developer.ninjatrader.com/docs/desktop/addplot\#examples)

### Indicator using various AddPlot() signatures

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";

     // Adds a blue line style plot
     AddPlot(Brushes.Blue, "MyPlot");

     // Adds a blue historgram style plot
     AddPlot(new Stroke(Brushes.Blue), PlotStyle.Bar, "MyPlot2");

     // Ensures that the width of the PlotStyle.Bar plot matches the width of the data series
     Plots[1].AutoWidth = true;

      // Adds a blue Dash-Line style plot with 5pixel width and 50% opacity
     AddPlot(new Stroke(Brushes.Blue, DashStyleHelper.Dash, 5, 50), PlotStyle.Line, "MyPlot3");
   }
}

```

### Indicator using a public `Series<double>` to expose a plot with a friendly name

## Note

This is required for making plots accessible in the strategy builder. For an example on exposing other variables publicly, see [exposing indicator values that are not plots](https://developer.ninjatrader.com/docs/desktop/exposing_indicator_values_that_are_not_plots)

```jsx-150469391 csharp
protected override void OnStateChange()

{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
     // Adds a blue line style plot
     AddPlot(Brushes.Blue, "MyPlot");
     // Adds a blue historgram style plot
     AddPlot(new Stroke(Brushes.Blue), PlotStyle.Bar, "MyPlot2");
   }
}
protected override void OnBarUpdate()
{
   MyPlot[0] = Close[0] + High[0] / 2​;
   MyPlot[1] = Close[0] + High[0] / 2​;
}
[Browsable(false)]
[XmlIgnore]
public Series<double> MyPlot
{
   get { return Values[0]; }
}
[Browsable(false)]
[XmlIgnore]
public Series<double> MyPlot2
{
   get { return Values[1]; }
}

```

### Indicator which adds three value series

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Examples Indicator";
     // Add three plots and associated Series<double> objects
     AddPlot(Brushes.Blue, "PlotA");     // Defines the plot for Values[0]
     AddPlot(Brushes.Red, "PlotB");     // Defines the plot for Values[1]
     AddPlot(Brushes.Green, "PlotC");   // Defines the plot for Values[2]
   }
}
protected override void OnBarUpdate()
{
   Values[0][0] = Median[0];   // Blue "Plot A"
   Values[1][0] = Low[0];       // Red "Plot B"
   Values[2][0] = High[0];     // Green "Plot C"
}

```

### Indicator which dynamically adds a plot in state.configure

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name                 = "Examples Indicator";
     // logical property which user can set
     UseSpecialMode   = false;
     // Default brush selection pushed to the UI
     MyBrush = Brushes.Red;
   }
   else if (State == State.Configure)
   {
     // if user enables logical property
     if (UseSpecialMode)
     {
         // add plot using default selected brush and special plot name
         AddPlot(MyBrush, "My Special Plot");
     }
     else
     {
         // otherwise use default selected brush and regular plot name
         AddPlot(MyBrush, "My Regular Plot");
     }
   }
}
protected override void OnBarUpdate()
{
   if (UseSpecialMode)
     Value[0] = Close[0] + High[0] / 2;
   else Value[0] = Close[0] * TickSize / 2;
}
[XmlIgnore]
public Brush MyBrush { get; set; }
public bool UseSpecialMode { get; set; }

```