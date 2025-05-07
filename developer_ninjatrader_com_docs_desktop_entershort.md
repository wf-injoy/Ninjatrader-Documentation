## [Definition](https://developer.ninjatrader.com/docs/desktop/entershort\#definition)

Generates a sell short market order to enter a short position.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/entershort\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/entershort\#syntax)

`EnterShort()`

`EnterShort(string signalName)`

`EnterShort(int quantity)`

`EnterShort(int quantity, string signalName)`

The following method variation is for experienced programmers who fully understand [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) concepts:

`EnterShort(int barsInProgressIndex, int quantity, string signalName)`

## Note

If using a method signature that does not have the parameter quantity, the order quantity will be taken from the quantity value set in the strategy dialog window when running or backtesting a strategy.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/entershort\#parameters)

| Parameter | Description |
| --- | --- |
| **signalName** | User defined signal name identifying the order generated. Max 50 characters. |
| **quantity** | Entry order quantity (if 0 is passed in, will be set to 1, except for stocks 100). |
| **barsInProgressIndex** | The index of the Bars object the order is to be submitted against. Used to determine what instrument the order is submitted for. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/entershort\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CurrentBar < 20)
         return;

     // Only enter if at least 10 bars has passed since our last entry
     if ((BarsSinceEntryExecution() > 10 || BarsSinceEntryExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
         EnterShort("SMA Cross Entry");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/entershort\#definition)

Generates a sell short market order to enter a short position.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/entershort\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/entershort\#syntax)

`EnterShort()`

`EnterShort(string signalName)`

`EnterShort(int quantity)`

`EnterShort(int quantity, string signalName)`

The following method variation is for experienced programmers who fully understand [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) concepts:

`EnterShort(int barsInProgressIndex, int quantity, string signalName)`

## Note

If using a method signature that does not have the parameter quantity, the order quantity will be taken from the quantity value set in the strategy dialog window when running or backtesting a strategy.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/entershort\#parameters)

| Parameter | Description |
| --- | --- |
| **signalName** | User defined signal name identifying the order generated. Max 50 characters. |
| **quantity** | Entry order quantity (if 0 is passed in, will be set to 1, except for stocks 100). |
| **barsInProgressIndex** | The index of the Bars object the order is to be submitted against. Used to determine what instrument the order is submitted for. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/entershort\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     if (CurrentBar < 20)
         return;

     // Only enter if at least 10 bars has passed since our last entry
     if ((BarsSinceEntryExecution() > 10 || BarsSinceEntryExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
         EnterShort("SMA Cross Entry");
}

```