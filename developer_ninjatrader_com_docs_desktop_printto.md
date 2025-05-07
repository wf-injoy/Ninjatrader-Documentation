## [Definition](https://developer.ninjatrader.com/docs/desktop/printto\#definition)

Determines either tab of the NinjaScript **Output window** the **Print()** and **ClearOutputWindow()** method targets.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/printto\#property-value)

An enum value representing the target Output Tab. The default value is **PrintTo.OutputTab1**.

Possible values are:

| **PrintTo.OutputTab1** | Output Windows tab named "Output 1" |
| **PrintTo.OutputTab2** | Output Windows tab named "Output 2" |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/printto\#syntax)

`PrintTo`

## [Examples](https://developer.ninjatrader.com/docs/desktop/printto\#examples)

### Setting the default PrintTo in separate scripts (\#1)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Sample PrintTo Indicator #1";
     Description = @"Used to Print updates to Output 1";

     //Set this scripts Print() calls to the first output tab
     PrintTo = PrintTo.OutputTab1;
   }
}

protected override void OnBarUpdate()
{
   Print("This script will print messages to Output Tab 1");
}

```

### Setting the default PrintTo in separate scripts (\#2)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Sample PrintTo Indicator #2";
    Description = "@Used to Print updates to Output 2";

     //Set this scripts Print() calls to the second output tab
     PrintTo = PrintTo.OutputTab2;
   }
}

protected override void OnBarUpdate()
{
   Print("This script will print messages to Output Tab 2");
}

```

### Setting PrintTo conditionally in a single script

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
   if(marketDataUpdate.MarketDataType == MarketDataType.Ask)
   {
     //Print Ask updates to Output 1
     PrintTo = PrintTo.OutputTab1;
     Print("Ask: " + marketDataUpdate.Price);
   }

   else if (marketDataUpdate.MarketDataType == MarketDataType.Bid)
   {
     //Print Bid updates to Output 2
     PrintTo = PrintTo.OutputTab2;
     Print("Bid: " + marketDataUpdate.Price);
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/printto\#definition)

Determines either tab of the NinjaScript **Output window** the **Print()** and **ClearOutputWindow()** method targets.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/printto\#property-value)

An enum value representing the target Output Tab. The default value is **PrintTo.OutputTab1**.

Possible values are:

| **PrintTo.OutputTab1** | Output Windows tab named "Output 1" |
| **PrintTo.OutputTab2** | Output Windows tab named "Output 2" |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/printto\#syntax)

`PrintTo`

## [Examples](https://developer.ninjatrader.com/docs/desktop/printto\#examples)

### Setting the default PrintTo in separate scripts (\#1)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Sample PrintTo Indicator #1";
     Description = @"Used to Print updates to Output 1";

     //Set this scripts Print() calls to the first output tab
     PrintTo = PrintTo.OutputTab1;
   }
}

protected override void OnBarUpdate()
{
   Print("This script will print messages to Output Tab 1");
}

```

### Setting the default PrintTo in separate scripts (\#2)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name = "Sample PrintTo Indicator #2";
    Description = "@Used to Print updates to Output 2";

     //Set this scripts Print() calls to the second output tab
     PrintTo = PrintTo.OutputTab2;
   }
}

protected override void OnBarUpdate()
{
   Print("This script will print messages to Output Tab 2");
}

```

### Setting PrintTo conditionally in a single script

```jsx-150469391 csharp
protected override void OnMarketData(MarketDataEventArgs marketDataUpdate)
{
   if(marketDataUpdate.MarketDataType == MarketDataType.Ask)
   {
     //Print Ask updates to Output 1
     PrintTo = PrintTo.OutputTab1;
     Print("Ask: " + marketDataUpdate.Price);
   }

   else if (marketDataUpdate.MarketDataType == MarketDataType.Bid)
   {
     //Print Bid updates to Output 2
     PrintTo = PrintTo.OutputTab2;
     Print("Bid: " + marketDataUpdate.Price);
   }
}

```