## [Definition](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#definition)

An event driven method which is called on an incoming execution of an order managed by a strategy. An execution is another name for a fill of an order.

- An order can generate multiple executions (partial fills)
- **OnExecutionUpdate** is typically called after [**OnOrderUpdate()**](https://developer.ninjatrader.com/docs/desktop/onorderupdate)
- Only orders which have been submitted and managed by the strategy will call **OnExecutionUpdate()**
- Executions drive the strategy [**Position**](https://developer.ninjatrader.com/docs/desktop/position) object, which is updated when this method is called

## Note

- Programming in this environment is reserved for the more [advanced user](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling). If you are for example looking to protect a strategy managed position with a basic stop and target, then the [**Set() methods**](https://developer.ninjatrader.com/docs/desktop/managed_approach) would be more convenient.
- When connected to the Playback connection, it is possible for **OnExecutionUpdate()** to trigger in the middle of a call to **OnBarUpdate()**. The Sim101 account adds a simulated random delay for processing execution events, but the Playback connection triggers executions immediately, for the sake of consistency in backtesting. Because of this, **OnExecutionUpdate()** can appear to be triggered earlier than it would in live trading, or when simulation trading on a live connection.
- Please also review [**Multi-Thread Considerations for NinjaScript**](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript).
- Its best practice to only work with the passed by value parameters and not reference parameters. This insures that you process each change of the underlying state.
- Rithmic and Interactive Brokers Users: When using a NinjaScript strategy it is best practice to only work with passed by value data from **OnExecutionUpdate()**. Instances of multiple fills at the same time for the same instrument might result in an incorrect **OnPositionUpdate**, as sequence of events are not guaranteed due to provider API design.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#syntax)

You must override the method in your strategy with the following syntax:

**protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)**

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#parameters)

| **execution** | An [**Execution**](https://developer.ninjatrader.com/docs/desktop/execution) object passed by reference representing the execution |
| **executionId** | A **string** value representing the execution id |
| **price** | A **double** value representing the execution price |
| **quantity** | An **int** value representing the execution quantity |
| **marketPosition** | A [**MarketPosition**](https://developer.ninjatrader.com/docs/desktop/marketposition) object representing the position of the execution. Possible values are:<br>- **MarketPosition.Long**<br>- **MarketPosition.Short** |
| **orderId** | A string representing the order id |
| **time** | A [**DateTime**](http://msdn.microsoft.com/en-us/library/system.datetime.aspx) value representing the time of the execution |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#examples)

## Note

**OnExecutionUpdate** Example (See [**SampleOnOrderUpdate**](https://developer.ninjatrader.com/docs/desktop/using_onorderupdate_and_onexec) for complete example)

```jsx-150469391 csharp
private Order entryOrder = null; // This variable holds an object representing our entry order
private Order stopOrder = null; // This variable holds an object representing our stop loss order
private Order targetOrder = null; // This variable holds an object representing our profit target order
private int sumFilled = 0; // This variable tracks the quantities of each execution making up the entry order

protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    /* We advise monitoring OnExecutionUpdate() to trigger submission of stop/target orders instead of OnOrderUpdate() since OnExecution() is called after OnOrderUpdate()
    which ensures your strategy has received the execution which is used for internal signal tracking. */
    if (entryOrder != null && entryOrder == execution.Order)
    {
        if (execution.Order.OrderState == OrderState.Filled || execution.Order.OrderState == OrderState.PartFilled || (execution.Order.OrderState == OrderState.Cancelled && execution.Order.Filled > 0))
        {
            // We sum the quantities of each execution making up the entry order
            sumFilled += execution.Quantity;

            // Submit exit orders for partial fills
            if (execution.Order.OrderState == OrderState.PartFilled)
            {
                stopOrder = ExitLongStopMarket(0, true, execution.Order.Filled, execution.Order.AverageFillPrice - 4 * TickSize, "MyStop", "MyEntry");
                targetOrder = ExitLongLimit(0, true, execution.Order.Filled, execution.Order.AverageFillPrice + 8 * TickSize, "MyTarget", "MyEntry");
            }
            // Update our exit order quantities once orderstate turns to filled and we have seen execution quantities match order quantities
            else if (execution.Order.OrderState == OrderState.Filled && sumFilled == execution.Order.Filled)
            {
                // Stop-Loss order for OrderState.Filled
                stopOrder = ExitLongStopMarket(0, true, execution.Order.Filled, execution.Order.AverageFillPrice - 4 * TickSize, "MyStop", "MyEntry");
                targetOrder = ExitLongLimit(0, true, execution.Order.Filled, execution.Order.AverageFillPrice + 8 * TickSize, "MyTarget", "MyEntry");
            }

            // Resets the entryOrder object and the sumFilled counter to null / 0 after the order has been filled
            if (execution.Order.OrderState != OrderState.PartFilled && sumFilled == execution.Order.Filled)
            {
                entryOrder = null;
                sumFilled = 0;
            }
        }
    }

    // Reset our stop order and target orders' Order objects after our position is closed. (1st Entry)
    if ((stopOrder != null && stopOrder == execution.Order) || (targetOrder != null && targetOrder == execution.Order))
    {
        if (execution.Order.OrderState == OrderState.Filled || execution.Order.OrderState == OrderState.PartFilled)
        {
            stopOrder = null;
            targetOrder = null;
        }
    }
}

```

## [Additional Reference Samples](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#additional-reference-samples)

Additional reference code samples are available in the NinjaScript Educational Resources section of our support forum.

## [Definition](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#definition)

An event driven method which is called on an incoming execution of an order managed by a strategy. An execution is another name for a fill of an order.

- An order can generate multiple executions (partial fills)
- **OnExecutionUpdate** is typically called after [**OnOrderUpdate()**](https://developer.ninjatrader.com/docs/desktop/onorderupdate)
- Only orders which have been submitted and managed by the strategy will call **OnExecutionUpdate()**
- Executions drive the strategy [**Position**](https://developer.ninjatrader.com/docs/desktop/position) object, which is updated when this method is called

## Note

- Programming in this environment is reserved for the more [advanced user](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling). If you are for example looking to protect a strategy managed position with a basic stop and target, then the [**Set() methods**](https://developer.ninjatrader.com/docs/desktop/managed_approach) would be more convenient.
- When connected to the Playback connection, it is possible for **OnExecutionUpdate()** to trigger in the middle of a call to **OnBarUpdate()**. The Sim101 account adds a simulated random delay for processing execution events, but the Playback connection triggers executions immediately, for the sake of consistency in backtesting. Because of this, **OnExecutionUpdate()** can appear to be triggered earlier than it would in live trading, or when simulation trading on a live connection.
- Please also review [**Multi-Thread Considerations for NinjaScript**](https://developer.ninjatrader.com/docs/desktop/multi_threading_consideration_for_ninjascript).
- Its best practice to only work with the passed by value parameters and not reference parameters. This insures that you process each change of the underlying state.
- Rithmic and Interactive Brokers Users: When using a NinjaScript strategy it is best practice to only work with passed by value data from **OnExecutionUpdate()**. Instances of multiple fills at the same time for the same instrument might result in an incorrect **OnPositionUpdate**, as sequence of events are not guaranteed due to provider API design.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#syntax)

You must override the method in your strategy with the following syntax:

**protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)**

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#parameters)

| **execution** | An [**Execution**](https://developer.ninjatrader.com/docs/desktop/execution) object passed by reference representing the execution |
| **executionId** | A **string** value representing the execution id |
| **price** | A **double** value representing the execution price |
| **quantity** | An **int** value representing the execution quantity |
| **marketPosition** | A [**MarketPosition**](https://developer.ninjatrader.com/docs/desktop/marketposition) object representing the position of the execution. Possible values are:<br>- **MarketPosition.Long**<br>- **MarketPosition.Short** |
| **orderId** | A string representing the order id |
| **time** | A [**DateTime**](http://msdn.microsoft.com/en-us/library/system.datetime.aspx) value representing the time of the execution |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#examples)

## Note

**OnExecutionUpdate** Example (See [**SampleOnOrderUpdate**](https://developer.ninjatrader.com/docs/desktop/using_onorderupdate_and_onexec) for complete example)

```jsx-150469391 csharp
private Order entryOrder = null; // This variable holds an object representing our entry order
private Order stopOrder = null; // This variable holds an object representing our stop loss order
private Order targetOrder = null; // This variable holds an object representing our profit target order
private int sumFilled = 0; // This variable tracks the quantities of each execution making up the entry order

protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    /* We advise monitoring OnExecutionUpdate() to trigger submission of stop/target orders instead of OnOrderUpdate() since OnExecution() is called after OnOrderUpdate()
    which ensures your strategy has received the execution which is used for internal signal tracking. */
    if (entryOrder != null && entryOrder == execution.Order)
    {
        if (execution.Order.OrderState == OrderState.Filled || execution.Order.OrderState == OrderState.PartFilled || (execution.Order.OrderState == OrderState.Cancelled && execution.Order.Filled > 0))
        {
            // We sum the quantities of each execution making up the entry order
            sumFilled += execution.Quantity;

            // Submit exit orders for partial fills
            if (execution.Order.OrderState == OrderState.PartFilled)
            {
                stopOrder = ExitLongStopMarket(0, true, execution.Order.Filled, execution.Order.AverageFillPrice - 4 * TickSize, "MyStop", "MyEntry");
                targetOrder = ExitLongLimit(0, true, execution.Order.Filled, execution.Order.AverageFillPrice + 8 * TickSize, "MyTarget", "MyEntry");
            }
            // Update our exit order quantities once orderstate turns to filled and we have seen execution quantities match order quantities
            else if (execution.Order.OrderState == OrderState.Filled && sumFilled == execution.Order.Filled)
            {
                // Stop-Loss order for OrderState.Filled
                stopOrder = ExitLongStopMarket(0, true, execution.Order.Filled, execution.Order.AverageFillPrice - 4 * TickSize, "MyStop", "MyEntry");
                targetOrder = ExitLongLimit(0, true, execution.Order.Filled, execution.Order.AverageFillPrice + 8 * TickSize, "MyTarget", "MyEntry");
            }

            // Resets the entryOrder object and the sumFilled counter to null / 0 after the order has been filled
            if (execution.Order.OrderState != OrderState.PartFilled && sumFilled == execution.Order.Filled)
            {
                entryOrder = null;
                sumFilled = 0;
            }
        }
    }

    // Reset our stop order and target orders' Order objects after our position is closed. (1st Entry)
    if ((stopOrder != null && stopOrder == execution.Order) || (targetOrder != null && targetOrder == execution.Order))
    {
        if (execution.Order.OrderState == OrderState.Filled || execution.Order.OrderState == OrderState.PartFilled)
        {
            stopOrder = null;
            targetOrder = null;
        }
    }
}

```

## [Additional Reference Samples](https://developer.ninjatrader.com/docs/desktop/onexecutionupdate\#additional-reference-samples)

Additional reference code samples are available in the NinjaScript Educational Resources section of our support forum.