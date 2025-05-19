## [Definition](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#definition)

Called every time an [order](https://developer.ninjatrader.com/docs/desktop/order) changes state. An order will change state when a change in order quantity, price or state (e.g. working to filled) occurs.

## Note

The OnOrderUpdate() method is called on ALL order updates (e.g., any account and instrument combination) and NOT just the specific items which are selected in the SuperDOM.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#syntax)

`protected override void OnOrderUpdate(OrderEventArgs orderUpdate)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#method-parameters)

| Parameter | Description |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#examples)

```jsx-150469391 csharp
protected override void OnOrderUpdate(OrderEventArgs orderUpdate)
{
  // Do not take action if the order update does not come from the selected SuperDOM instrument/account
  if (orderUpdate.Order.Instrument != SuperDom.Instrument || orderUpdate.Order.Account != SuperDom.Account)
    return;

  // Do something
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#definition)

Called every time an [order](https://developer.ninjatrader.com/docs/desktop/order) changes state. An order will change state when a change in order quantity, price or state (e.g. working to filled) occurs.

## Note

The OnOrderUpdate() method is called on ALL order updates (e.g., any account and instrument combination) and NOT just the specific items which are selected in the SuperDOM.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#syntax)

`protected override void OnOrderUpdate(OrderEventArgs orderUpdate)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#method-parameters)

| Parameter | Description |
| --- | --- |

## [Examples](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate\#examples)

```jsx-150469391 csharp
protected override void OnOrderUpdate(OrderEventArgs orderUpdate)
{
  // Do not take action if the order update does not come from the selected SuperDOM instrument/account
  if (orderUpdate.Order.Instrument != SuperDom.Instrument || orderUpdate.Order.Account != SuperDom.Account)
    return;

  // Do something
}

```