## [Definition](https://developer.ninjatrader.com/docs/desktop/execution\#definition)

Represents a read only interface that exposes information regarding an execution (filled order) resulting from an order and is passed as a parameter in the **OnExecutionUpdate()** method.

## Note

Not all executions will have associated **Order** objects (e.g **ExitOnSessionClose** executions or **AtmStrategyCreate()** executions)

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/execution\#methods-and-properties)

| Property | Description |
| --- | --- |
| Account | The **Account** the execution occurred |
| BarsInProgress | An **int** value representing the **BarsArray** in which the execution occurred |
| Commission | A **double** value representing the commission of an execution |
| ExecutionId | A **string** value representing the exchange generated execution id |
| Instrument | An **Instrument** value representing the instrument of an order |
| MarketPosition | The position of the execution. Possible values are: _MarketPosition.Long_ _MarketPosition.Short_ |
| Name | A string representing the name of an order which can be provided by the entry or exit signal name |
| Order | An **Order** value representing an order associated to the execution. |
| OrderId | A string representing the unique id of the order which was executed |
| Position | An **int** value represents the current quantity of account position at the time of execution |
| PositionStrategy | An **int** value represents the current quantity of strategy position at the time of execution |
| Price | A **double** value representing the price of an execution |
| Quantity | An **int** value representing quantity of an execution |
| Rate | A **double** value representing the exchange rate calculated for non-USD base products (1 if no rate was applied) |
| Slippage | A **double** value representing the number of ticks calculated between the last trade price and the execution price |
| Time | A **DateTime** structure representing the time the execution occurred |
| ToString() | A string representation of an execution |

## [Examples](https://developer.ninjatrader.com/docs/desktop/execution\#examples)

### Finding the executions of a particular Order object

```jsx-150469391 csharp
// Example #1
private Order entryOrder = null;

protected override void OnBarUpdate()
{
    if (entryOrder == null && Close[0] > Open[0])
        EnterLong("myEntryOrder");
}

protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    // Assign entryOrder in OnExecutionUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not guaranteed to be complete if it is referenced immediately after submitting
    if (execution.Order.Name == "myEntryOrder" && execution.Order.OrderState == OrderState.Filled)
        entryOrder = execution.order;

    if (entryOrder != null && entryOrder == execution.Order)
        Print(execution.ToString());
}

```

### Generic execution logic not specific to a particular Order object

```jsx-150469391 csharp
// Example #2
protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    // Remember to check the underlying Order object for null before trying to access its properties
    if (execution.Order != null && execution.Order.OrderState == OrderState.Filled)
        Print(execution.ToString());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/execution\#definition)

Represents a read only interface that exposes information regarding an execution (filled order) resulting from an order and is passed as a parameter in the **OnExecutionUpdate()** method.

## Note

Not all executions will have associated **Order** objects (e.g **ExitOnSessionClose** executions or **AtmStrategyCreate()** executions)

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/execution\#methods-and-properties)

| Property | Description |
| --- | --- |
| Account | The **Account** the execution occurred |
| BarsInProgress | An **int** value representing the **BarsArray** in which the execution occurred |
| Commission | A **double** value representing the commission of an execution |
| ExecutionId | A **string** value representing the exchange generated execution id |
| Instrument | An **Instrument** value representing the instrument of an order |
| MarketPosition | The position of the execution. Possible values are: _MarketPosition.Long_ _MarketPosition.Short_ |
| Name | A string representing the name of an order which can be provided by the entry or exit signal name |
| Order | An **Order** value representing an order associated to the execution. |
| OrderId | A string representing the unique id of the order which was executed |
| Position | An **int** value represents the current quantity of account position at the time of execution |
| PositionStrategy | An **int** value represents the current quantity of strategy position at the time of execution |
| Price | A **double** value representing the price of an execution |
| Quantity | An **int** value representing quantity of an execution |
| Rate | A **double** value representing the exchange rate calculated for non-USD base products (1 if no rate was applied) |
| Slippage | A **double** value representing the number of ticks calculated between the last trade price and the execution price |
| Time | A **DateTime** structure representing the time the execution occurred |
| ToString() | A string representation of an execution |

## [Examples](https://developer.ninjatrader.com/docs/desktop/execution\#examples)

### Finding the executions of a particular Order object

```jsx-150469391 csharp
// Example #1
private Order entryOrder = null;

protected override void OnBarUpdate()
{
    if (entryOrder == null && Close[0] > Open[0])
        EnterLong("myEntryOrder");
}

protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    // Assign entryOrder in OnExecutionUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not guaranteed to be complete if it is referenced immediately after submitting
    if (execution.Order.Name == "myEntryOrder" && execution.Order.OrderState == OrderState.Filled)
        entryOrder = execution.order;

    if (entryOrder != null && entryOrder == execution.Order)
        Print(execution.ToString());
}

```

### Generic execution logic not specific to a particular Order object

```jsx-150469391 csharp
// Example #2
protected override void OnExecutionUpdate(Execution execution, string executionId, double price, int quantity, MarketPosition marketPosition, string orderId, DateTime time)
{
    // Remember to check the underlying Order object for null before trying to access its properties
    if (execution.Order != null && execution.Order.OrderState == OrderState.Filled)
        Print(execution.ToString());
}

```