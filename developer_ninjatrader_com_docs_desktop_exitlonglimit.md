## [Definition](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#definition)

Generates a sell limit order to exit a long position.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#syntax)

`ExitLongLimit(double limitPrice)`

`ExitLongLimit(int quantity, double limitPrice)`

`ExitLongLimit(double limitPrice, string fromEntrySignal)`

`ExitLongLimit(double limitPrice, string signalName, string fromEntrySignal)`

`ExitLongLimit(int quantity, double limitPrice, string signalName, string fromEntrySignal)`

The following method variation is for experienced programmers who fully understand [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) concepts:

`ExitLongLimit(int barsInProgressIndex, bool isLiveUntilCancelled, int quantity, double limitPrice, string signalName, string fromEntrySignal)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#parameters)

| signalName | User defined signal name identifying the order generated. Max 50 characters. |
| --- | --- |
| fromEntrySignal | The entry signal name. This ties the exit to the entry and exits the position quantity represented by the actual entry. Note: Using an empty string will attach the exit order to all entries. |
| limitPrice | The limit price of the order. |
| quantity | Entry order quantity. |
| isLiveUntilCancelled | The order will NOT expire at the end of a bar but instead remain live until the **CancelOrder()** method is called or its time in force is reached. |
| barsInProgressIndex | The index of the Bars object the order is to be submitted against. Used to determine what instrument the order is submitted for. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (CurrentBar < 20)
        return;

    // Only enter if at least 10 bars has passed since our last entry
    if ((BarsSinceEntryExecution() > 10 || BarsSinceEntryExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
        EnterLong("SMA Cross Entry");

    // Exits position
    if (CrossBelow(SMA(10), SMA(20), 1))
        ExitLongLimit(GetCurrentBid());
}

```

## [Tips](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#tips)

## Note

- This method is ignored if a long position does not exist.
- It is helpful to provide a signal name if your strategy has multiple exit points to help identify your exits on a chart.
- You can tie an exit to an entry by providing the entry signal name in the parameter "fromEntrySignal".
- If you do not specify a quantity the entire position is exited rendering your strategy flat.
- If you do not specify a "fromEntrySignal" parameter the entire position is exited rendering your strategy flat.

## [Definition](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#definition)

Generates a sell limit order to exit a long position.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#syntax)

`ExitLongLimit(double limitPrice)`

`ExitLongLimit(int quantity, double limitPrice)`

`ExitLongLimit(double limitPrice, string fromEntrySignal)`

`ExitLongLimit(double limitPrice, string signalName, string fromEntrySignal)`

`ExitLongLimit(int quantity, double limitPrice, string signalName, string fromEntrySignal)`

The following method variation is for experienced programmers who fully understand [Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling) concepts:

`ExitLongLimit(int barsInProgressIndex, bool isLiveUntilCancelled, int quantity, double limitPrice, string signalName, string fromEntrySignal)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#parameters)

| signalName | User defined signal name identifying the order generated. Max 50 characters. |
| --- | --- |
| fromEntrySignal | The entry signal name. This ties the exit to the entry and exits the position quantity represented by the actual entry. Note: Using an empty string will attach the exit order to all entries. |
| limitPrice | The limit price of the order. |
| quantity | Entry order quantity. |
| isLiveUntilCancelled | The order will NOT expire at the end of a bar but instead remain live until the **CancelOrder()** method is called or its time in force is reached. |
| barsInProgressIndex | The index of the Bars object the order is to be submitted against. Used to determine what instrument the order is submitted for. See the [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) property. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (CurrentBar < 20)
        return;

    // Only enter if at least 10 bars has passed since our last entry
    if ((BarsSinceEntryExecution() > 10 || BarsSinceEntryExecution() == -1) && CrossAbove(SMA(10), SMA(20), 1))
        EnterLong("SMA Cross Entry");

    // Exits position
    if (CrossBelow(SMA(10), SMA(20), 1))
        ExitLongLimit(GetCurrentBid());
}

```

## [Tips](https://developer.ninjatrader.com/docs/desktop/exitlonglimit\#tips)

## Note

- This method is ignored if a long position does not exist.
- It is helpful to provide a signal name if your strategy has multiple exit points to help identify your exits on a chart.
- You can tie an exit to an entry by providing the entry signal name in the parameter "fromEntrySignal".
- If you do not specify a quantity the entire position is exited rendering your strategy flat.
- If you do not specify a "fromEntrySignal" parameter the entire position is exited rendering your strategy flat.