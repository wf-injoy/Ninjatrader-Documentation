## [Definition](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#definition)

Generates an **Unmanaged** order.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the **Unmanaged Approach** section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#syntax)

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice, string oco)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice, string oco, string signalName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#parameters)

| Parameter | Description |
| --- | --- |
| selectedBarsInProgress | The index of the Bars object the order is to be submitted against. This determines what instrument the order is submitted for. Note: See the **BarsInProgress** property. |
| orderAction | Determines if the order is a buy or sell order. Possible values:<br>- **OrderAction.Buy**<br>- **OrderAction.BuyToCover**<br>- **OrderAction.Sell**<br>- **OrderAction.SellShort** |
| orderType | Determines the type of order submitted<br>Possible values:<br>- **OrderType.Limit**<br>- **OrderType.Market**<br>- **OrderType.MIT**<br>- **OrderType.StopMarket**<br>- **OrderType.StopLimit** |
| quantity | Sets the number of contracts to submit with the order |
| limitPrice | Order limit price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| stopPrice | Order stop price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| oco | A string representing the OCO ID used to link OCO orders together<br>Note: OCO strings should not be reused. Use unique strings for each OCO group, and reset after orders in that group are filled/canceled |
| signalName | A string representing the name of the order. Max 50 characters. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#examples)

```jsx-150469391 csharp
private Order entryOrder = null;
protected override void OnBarUpdate()
{
    // Entry condition
    if (Close[0] > SMA(20)[0] && entryOrder == null)
        SubmitOrderUnmanaged(0, OrderAction.Buy, OrderType.Market, 1, 0, 0, "", "Enter Long");
}
protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
    // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not guaranteed to be complete if it is referenced immediately after submitting
    if (order.Name == "Enter Long" && orderState == OrderState.Filled)
        entryOrder = order;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#definition)

Generates an **Unmanaged** order.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#method-return-value)

An **Order** read-only object that represents the order. Reserved for experienced programmers, additional information can be found within the **Unmanaged Approach** section.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#syntax)

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice, string oco)`

`SubmitOrderUnmanaged(int selectedBarsInProgress, OrderAction orderAction, OrderType orderType, int quantity, double limitPrice, double stopPrice, string oco, string signalName)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#parameters)

| Parameter | Description |
| --- | --- |
| selectedBarsInProgress | The index of the Bars object the order is to be submitted against. This determines what instrument the order is submitted for. Note: See the **BarsInProgress** property. |
| orderAction | Determines if the order is a buy or sell order. Possible values:<br>- **OrderAction.Buy**<br>- **OrderAction.BuyToCover**<br>- **OrderAction.Sell**<br>- **OrderAction.SellShort** |
| orderType | Determines the type of order submitted<br>Possible values:<br>- **OrderType.Limit**<br>- **OrderType.Market**<br>- **OrderType.MIT**<br>- **OrderType.StopMarket**<br>- **OrderType.StopLimit** |
| quantity | Sets the number of contracts to submit with the order |
| limitPrice | Order limit price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| stopPrice | Order stop price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| oco | A string representing the OCO ID used to link OCO orders together<br>Note: OCO strings should not be reused. Use unique strings for each OCO group, and reset after orders in that group are filled/canceled |
| signalName | A string representing the name of the order. Max 50 characters. |

## [Examples](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged\#examples)

```jsx-150469391 csharp
private Order entryOrder = null;
protected override void OnBarUpdate()
{
    // Entry condition
    if (Close[0] > SMA(20)[0] && entryOrder == null)
        SubmitOrderUnmanaged(0, OrderAction.Buy, OrderType.Market, 1, 0, 0, "", "Enter Long");
}
protected override void OnOrderUpdate(Order order, double limitPrice, double stopPrice, int quantity, int filled, double averageFillPrice, OrderState orderState, DateTime time, ErrorCode error, string nativeError)
{
    // Assign entryOrder in OnOrderUpdate() to ensure the assignment occurs when expected.
    // This is more reliable than assigning Order objects in OnBarUpdate, as the assignment is not guaranteed to be complete if it is referenced immediately after submitting
    if (order.Name == "Enter Long" && orderState == OrderState.Filled)
        entryOrder = order;
}

```