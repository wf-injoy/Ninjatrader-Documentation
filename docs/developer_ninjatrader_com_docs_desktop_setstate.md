## [Definition](https://developer.ninjatrader.com/docs/desktop/setstate\#definition)

This method is used for changing the `State` of any running NinjaScript object.

## Note

Notes:

- Attempting to set a State earlier than the current State will be ignored.
- Calling **SetState()** multiple times will be ignored to prevent the object from erroneously setting states unexpectedly.
- Setting State to **State.Terminated** is meant as a way to abort the strategy as it is running. Doing this in a Strategy Analyzer backtest will abort the backtest entirely, and no partial backtest results will be shown.
- After setting **State.Terminated**, you should return from the calling method to help ensure subsequent logic is not processed asynchronously to **OnStateChange()**.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/setstate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setstate\#syntax)

`SetState(State state)`

## Warning

This method should only be called after the `State` reaches **State.DataLoaded**.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/setstate\#parameters)

| Parameter | Description |
| --- | --- |
| **state** | The **State** to be set |

## [Examples](https://developer.ninjatrader.com/docs/desktop/setstate\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Terminate strategy at 2PM
   if (ToTime(Time[0]) == 140000)
   {
     SetState(State.Terminated);
     return;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/setstate\#definition)

This method is used for changing the `State` of any running NinjaScript object.

## Note

Notes:

- Attempting to set a State earlier than the current State will be ignored.
- Calling **SetState()** multiple times will be ignored to prevent the object from erroneously setting states unexpectedly.
- Setting State to **State.Terminated** is meant as a way to abort the strategy as it is running. Doing this in a Strategy Analyzer backtest will abort the backtest entirely, and no partial backtest results will be shown.
- After setting **State.Terminated**, you should return from the calling method to help ensure subsequent logic is not processed asynchronously to **OnStateChange()**.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/setstate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setstate\#syntax)

`SetState(State state)`

## Warning

This method should only be called after the `State` reaches **State.DataLoaded**.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/setstate\#parameters)

| Parameter | Description |
| --- | --- |
| **state** | The **State** to be set |

## [Examples](https://developer.ninjatrader.com/docs/desktop/setstate\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   // Terminate strategy at 2PM
   if (ToTime(Time[0]) == 140000)
   {
     SetState(State.Terminated);
     return;
   }
}

```