The **OnBarUpdate()** method is called for each incoming tick, or on the close of a bar (if enabled) when performing real-time calculations, and is called on each bar of a **Bars** object when re-calculating the indicator (For example, an indicator would be re-calculated when adding it to an existing chart that has existing price data displayed). This is the main method used for indicator calculations, and we will calculate our core indicator logic (testing to see if a Close price on a specified bar was greater than the previous Close price) within this method.

## [Adding the Condition and Assigning the Plot Value](https://developer.ninjatrader.com/docs/desktop/entering_calculation_logic\#adding-the-condition-and-assigning-the-plot-value)

Enter the following code in the **OnBarUpdate()** method in the NinjaScript Editor:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 *TickSize)) : (Low[BarsAgo] - (5* TickSize))

```

Although the code above fits on a single line, it is doing several things. Firstly, it is important to understand the structure that we are using in this statement. We are using a **Ternary Operator**, which provides a way to assign one of two values to a variable based on a condition. We begin by stating that we wish to assign a value to the indicator plot at a bar index corresponding to **BarsAgo**. We do this by using **Values**, which is a collection holding values for all plots configured in the indicator:

```jsx-1168641291 csharp
 Values[0][BarsAgo] =

```

Next, we add a condition to test. In this case, we are testing to see whether **Close** at a bar index corresponding to the value of **BarsAgo** was greater than **Close** at a value of **BarsAgo + 1**. If **BarsAgo** was set to 5, for example, this would compare **Close\[5\]** to **Close\[6\]**:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ?

```

If the condition evaluates to true, then the first expression will be run (the expression on the left side of the colon ":"), which will assign the value of the indicator plot to the **High** price of the specified bar, plus five ticks. We obtain the tick size value for the configured instrument via the **TickSize** property:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 * TickSize)) :

```

If the condition evaluates to false, then the second expression will be run (the expression on the right side of the colon ":", which will assign the value of the indicator plot to the **Low** price of the specified bar, less five ticks:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 *TickSize)) : (Low[BarsAgo] - (5* TickSize))

```

The core indicator logic is now in place, but running this code as it is can result in an "Index out of range" exception. Since we are looking a certain number of bars back in time, we need to make sure that there are always enough bars on the chart for us to look back. For example, if **BarsAgo** were set to 5, then we would be comparing the value of five bars ago to the value of six bars ago, but on Bars # 1, 2, 3, 4, or 5, at which point we do not have five or six bars to look back, the indicator will cause an error. To resolve this, we will add a condition which will prevent the core calculations from running unless we know there are enough bars on the chart. Add the following line just above the line you have been working on throughout this page:

```jsx-150469391 csharp
if(CurrentBar < BarsAgo + 1)
   return;

```

This line says, "if there is not a number of bars equal to one number greater than the value of **BarsAgo**, then exit **OnBarUpdate()**."

Now that everything is in place, your class code should look as below. You are now ready to **compile the indicator** and configure it on a chart:

```jsx-150469391 csharp
public class PriceVariableTutorial : Indicator
{
   protected override void OnStateChange()
   {
       if (State == State.SetDefaults)
       {
           Description                     = @"NinjaScript Price Variables Tutorial";
           Name                           = "PriceVariableTutorial";
           Calculate                       = Calculate.OnBarClose;
           IsOverlay                       = false;
           DisplayInDataBox               = true;
           DrawOnPricePanel               = true;
           DrawHorizontalGridLines         = true;
           DrawVerticalGridLines           = true;
           PaintPriceMarkers               = true;
           ScaleJustification               = NinjaTrader.Gui.Chart.ScaleJustification.Right;
           //Disable this property if your indicator requires custom values that cumulate with each new market data event.
           //See Help Guide for additional information.
           IsSuspendedWhileInactive       = true;
           BarsAgo                         = 0;
           AddPlot(Brushes.Orange, "MyPlot");
       }
       else if (State == State.Configure)
       {
       }
   }

   protected override void OnBarUpdate()
   {
       if(CurrentBar < BarsAgo + 1)
           return;

       Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 * TickSize)) : (Low[BarsAgo] - (5 * TickSize));
   }

   #region Properties
   [Range(0, int.MaxValue)]
   [NinjaScriptProperty]
   [Display(Name="BarsAgo", Description="How many bars ago to use for the plot value", Order=1)]
   public int BarsAgo
   { get; set; }

   [Browsable(false)]
   [XmlIgnore]
   public Series<double> MyPlot
   {
       get { return Values[0]; }
   }
   #endregion
}

```

The **OnBarUpdate()** method is called for each incoming tick, or on the close of a bar (if enabled) when performing real-time calculations, and is called on each bar of a **Bars** object when re-calculating the indicator (For example, an indicator would be re-calculated when adding it to an existing chart that has existing price data displayed). This is the main method used for indicator calculations, and we will calculate our core indicator logic (testing to see if a Close price on a specified bar was greater than the previous Close price) within this method.

## [Adding the Condition and Assigning the Plot Value](https://developer.ninjatrader.com/docs/desktop/entering_calculation_logic\#adding-the-condition-and-assigning-the-plot-value)

Enter the following code in the **OnBarUpdate()** method in the NinjaScript Editor:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 *TickSize)) : (Low[BarsAgo] - (5* TickSize))

```

Although the code above fits on a single line, it is doing several things. Firstly, it is important to understand the structure that we are using in this statement. We are using a **Ternary Operator**, which provides a way to assign one of two values to a variable based on a condition. We begin by stating that we wish to assign a value to the indicator plot at a bar index corresponding to **BarsAgo**. We do this by using **Values**, which is a collection holding values for all plots configured in the indicator:

```jsx-1168641291 csharp
 Values[0][BarsAgo] =

```

Next, we add a condition to test. In this case, we are testing to see whether **Close** at a bar index corresponding to the value of **BarsAgo** was greater than **Close** at a value of **BarsAgo + 1**. If **BarsAgo** was set to 5, for example, this would compare **Close\[5\]** to **Close\[6\]**:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ?

```

If the condition evaluates to true, then the first expression will be run (the expression on the left side of the colon ":"), which will assign the value of the indicator plot to the **High** price of the specified bar, plus five ticks. We obtain the tick size value for the configured instrument via the **TickSize** property:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 * TickSize)) :

```

If the condition evaluates to false, then the second expression will be run (the expression on the right side of the colon ":", which will assign the value of the indicator plot to the **Low** price of the specified bar, less five ticks:

```jsx-1168641291 csharp
Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 *TickSize)) : (Low[BarsAgo] - (5* TickSize))

```

The core indicator logic is now in place, but running this code as it is can result in an "Index out of range" exception. Since we are looking a certain number of bars back in time, we need to make sure that there are always enough bars on the chart for us to look back. For example, if **BarsAgo** were set to 5, then we would be comparing the value of five bars ago to the value of six bars ago, but on Bars # 1, 2, 3, 4, or 5, at which point we do not have five or six bars to look back, the indicator will cause an error. To resolve this, we will add a condition which will prevent the core calculations from running unless we know there are enough bars on the chart. Add the following line just above the line you have been working on throughout this page:

```jsx-150469391 csharp
if(CurrentBar < BarsAgo + 1)
   return;

```

This line says, "if there is not a number of bars equal to one number greater than the value of **BarsAgo**, then exit **OnBarUpdate()**."

Now that everything is in place, your class code should look as below. You are now ready to **compile the indicator** and configure it on a chart:

```jsx-150469391 csharp
public class PriceVariableTutorial : Indicator
{
   protected override void OnStateChange()
   {
       if (State == State.SetDefaults)
       {
           Description                     = @"NinjaScript Price Variables Tutorial";
           Name                           = "PriceVariableTutorial";
           Calculate                       = Calculate.OnBarClose;
           IsOverlay                       = false;
           DisplayInDataBox               = true;
           DrawOnPricePanel               = true;
           DrawHorizontalGridLines         = true;
           DrawVerticalGridLines           = true;
           PaintPriceMarkers               = true;
           ScaleJustification               = NinjaTrader.Gui.Chart.ScaleJustification.Right;
           //Disable this property if your indicator requires custom values that cumulate with each new market data event.
           //See Help Guide for additional information.
           IsSuspendedWhileInactive       = true;
           BarsAgo                         = 0;
           AddPlot(Brushes.Orange, "MyPlot");
       }
       else if (State == State.Configure)
       {
       }
   }

   protected override void OnBarUpdate()
   {
       if(CurrentBar < BarsAgo + 1)
           return;

       Values[0][BarsAgo] = (Close[BarsAgo] > Close[(BarsAgo + 1)]) ? (High[BarsAgo] + (5 * TickSize)) : (Low[BarsAgo] - (5 * TickSize));
   }

   #region Properties
   [Range(0, int.MaxValue)]
   [NinjaScriptProperty]
   [Display(Name="BarsAgo", Description="How many bars ago to use for the plot value", Order=1)]
   public int BarsAgo
   { get; set; }

   [Browsable(false)]
   [XmlIgnore]
   public Series<double> MyPlot
   {
       get { return Values[0]; }
   }
   #endregion
}

```