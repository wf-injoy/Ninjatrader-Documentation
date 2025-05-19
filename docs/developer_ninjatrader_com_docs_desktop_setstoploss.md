## [Definition](https://developer.ninjatrader.com/docs/desktop/setstoploss\#definition)

Generates a stop loss order with the signal name **Stop loss** used to exit a position. Stop loss orders are real working orders (unless simulated is specified in which case the stop order is locally simulated and submitted as market once triggered) submitted immediately to the market upon receiving an execution from an entry order.

## Note

Notes:

- Stop loss orders are submitted in real-time on incoming executions from entry orders.
- Since they are submitted upon receiving an execution, the Set method should be called prior to submitting the associated entry order to ensure an initial level is set.
- A strategy will either generate a stop loss order for each partial fill of an entry order or one order for all fills. See additional information under the [Strategies](https://ninjatrader.com/support/helpGuides/nt8/?options_strategies.htm) tab of the Options dialog window.
- If a [profit target](https://developer.ninjatrader.com/docs/desktop/setprofittarget) order is generated in addition to a stop loss order, they are submitted as OCO (one cancels other).
- Stop loss orders are submitted as stop-market orders.
- A stop loss order is automatically canceled if the managing position is closed by another strategy generated exit order.
- Should you have multiple Bars objects of the same instrument while using **SetStopLoss()** in your strategy, you should only submit orders for this instrument to the first Bars context of that instrument. This is to ensure your order logic is processed correctly and any necessary order amendments are done properly.
- The **SetStopLoss()** method can NOT be used concurrently with the [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) or [SetParabolicStop()](https://developer.ninjatrader.com/docs/desktop/setparabolicstop) method for the same position; if any methods are called for the same position (fromEntrySignal), the **SetStopLoss()** will always take precedence. You can however, use all three methods in the same strategy if they reference different signal names.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setstoploss\#syntax)

`SetStopLoss(CalculationMode mode, double value)`

`SetStopLoss(string fromEntrySignal, CalculationMode mode, double value, bool isSimulatedStop)`

## Warning

This method CANNOT be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.SetDefaults.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/setstoploss\#parameters)

| Parameter | Description |
| --- | --- |
| **mode** | Determines the manner in which the value parameter is calculated. Possible values are:<br>- **CalculationMode.Currency**: PnL away from average entry. Calculated by the dollar per tick value for the order quantity used. When this mode is used, [StopTargetHandling](https://developer.ninjatrader.com/docs/desktop/stoptargethandling) will automatically be set to ByStrategyPosition.<br>- **CalculationMode.Percent**: Percentage away from the average entry, based on the average entry price.<br>- **CalculationMode.Pips**: Pips away from average entry.<br>- **CalculationMode.Price**: The absolute price point specified.<br>- **CalculationMode.Ticks**: Ticks away from entry average entry. Please note in percentage calculation mode a value of 1 is equal to 100%, a value of 0.1 is equal to 10%, and a value of 0.01 will be 1%. |
| **isSimulatedStop** | If true, will simulate the stop order and submit as market once triggered. |
| **value** | The value the stop loss order is offset from the position entry price (exception is using .Price mode where 'value' will represent the actual price). |
| **fromEntrySignal** | The entry signal name. This ties the stop loss exit to the entry and exits the position quantity represented by the actual entry. Using an empty string will attach the exit order to all entries. |

## Note

Tips (also see [Overview](https://developer.ninjatrader.com/docs/desktop/managed_approach)):

- It is suggested to call this method from within the strategy [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method if your stop loss price/offset is static.
- You may call this method from within the strategy [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method should you wish to dynamically change the stop loss price while in an open position.
- Should you call this method to dynamically change the stop loss price in the strategy [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method, you should always reset the stop loss price / offset value when your strategy is flat; otherwise, the last price/offset value set will be used to generate your stop loss order on your next open position.
- The signal name generated internally by this method is **Stop loss** which can be used with various methods such as [BarsSinceExitExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution), or other order concepts which rely on identifying a signal name.

## [Examples](https://developer.ninjatrader.com/docs/desktop/setstoploss\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Submits a stop loss of $500
        SetStopLoss(CalculationMode.Currency, 500);
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/setstoploss\#definition)

Generates a stop loss order with the signal name **Stop loss** used to exit a position. Stop loss orders are real working orders (unless simulated is specified in which case the stop order is locally simulated and submitted as market once triggered) submitted immediately to the market upon receiving an execution from an entry order.

## Note

Notes:

- Stop loss orders are submitted in real-time on incoming executions from entry orders.
- Since they are submitted upon receiving an execution, the Set method should be called prior to submitting the associated entry order to ensure an initial level is set.
- A strategy will either generate a stop loss order for each partial fill of an entry order or one order for all fills. See additional information under the [Strategies](https://ninjatrader.com/support/helpGuides/nt8/?options_strategies.htm) tab of the Options dialog window.
- If a [profit target](https://developer.ninjatrader.com/docs/desktop/setprofittarget) order is generated in addition to a stop loss order, they are submitted as OCO (one cancels other).
- Stop loss orders are submitted as stop-market orders.
- A stop loss order is automatically canceled if the managing position is closed by another strategy generated exit order.
- Should you have multiple Bars objects of the same instrument while using **SetStopLoss()** in your strategy, you should only submit orders for this instrument to the first Bars context of that instrument. This is to ensure your order logic is processed correctly and any necessary order amendments are done properly.
- The **SetStopLoss()** method can NOT be used concurrently with the [SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop) or [SetParabolicStop()](https://developer.ninjatrader.com/docs/desktop/setparabolicstop) method for the same position; if any methods are called for the same position (fromEntrySignal), the **SetStopLoss()** will always take precedence. You can however, use all three methods in the same strategy if they reference different signal names.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setstoploss\#syntax)

`SetStopLoss(CalculationMode mode, double value)`

`SetStopLoss(string fromEntrySignal, CalculationMode mode, double value, bool isSimulatedStop)`

## Warning

This method CANNOT be called from the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method during State.SetDefaults.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/setstoploss\#parameters)

| Parameter | Description |
| --- | --- |
| **mode** | Determines the manner in which the value parameter is calculated. Possible values are:<br>- **CalculationMode.Currency**: PnL away from average entry. Calculated by the dollar per tick value for the order quantity used. When this mode is used, [StopTargetHandling](https://developer.ninjatrader.com/docs/desktop/stoptargethandling) will automatically be set to ByStrategyPosition.<br>- **CalculationMode.Percent**: Percentage away from the average entry, based on the average entry price.<br>- **CalculationMode.Pips**: Pips away from average entry.<br>- **CalculationMode.Price**: The absolute price point specified.<br>- **CalculationMode.Ticks**: Ticks away from entry average entry. Please note in percentage calculation mode a value of 1 is equal to 100%, a value of 0.1 is equal to 10%, and a value of 0.01 will be 1%. |
| **isSimulatedStop** | If true, will simulate the stop order and submit as market once triggered. |
| **value** | The value the stop loss order is offset from the position entry price (exception is using .Price mode where 'value' will represent the actual price). |
| **fromEntrySignal** | The entry signal name. This ties the stop loss exit to the entry and exits the position quantity represented by the actual entry. Using an empty string will attach the exit order to all entries. |

## Note

Tips (also see [Overview](https://developer.ninjatrader.com/docs/desktop/managed_approach)):

- It is suggested to call this method from within the strategy [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method if your stop loss price/offset is static.
- You may call this method from within the strategy [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method should you wish to dynamically change the stop loss price while in an open position.
- Should you call this method to dynamically change the stop loss price in the strategy [OnBarUpdate()](https://developer.ninjatrader.com/docs/desktop/onbarupdate) method, you should always reset the stop loss price / offset value when your strategy is flat; otherwise, the last price/offset value set will be used to generate your stop loss order on your next open position.
- The signal name generated internally by this method is **Stop loss** which can be used with various methods such as [BarsSinceExitExecution()](https://developer.ninjatrader.com/docs/desktop/barssinceexitexecution), or other order concepts which rely on identifying a signal name.

## [Examples](https://developer.ninjatrader.com/docs/desktop/setstoploss\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.Configure)
    {
        // Submits a stop loss of $500
        SetStopLoss(CalculationMode.Currency, 500);
    }
}

```