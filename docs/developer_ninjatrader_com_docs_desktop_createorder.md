## [Definition](https://developer.ninjatrader.com/docs/desktop/createorder\#definition)

Creates an **Order** to be submitted via **Submit()**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/createorder\#syntax)

`CreateOrder(Instrument instrument, OrderAction action, OrderType orderType, OrderEntry orderEntry, TimeInForce timeInForce, int quantity, double limitPrice, double stopPrice, string oco, string name, DateTime gtd, CustomOrder customOrder)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/createorder\#parameters)

| **instrument** | Order instrument |
| **orderAction** | Possible values:<br>- **OrderAction.Buy**<br>- **OrderAction.BuyToCover**<br>- **OrderAction.Sell**<br>- **OrderAction.SellShort** |
| **orderType** | Possible values:<br>- **OrderType.Limit**<br>- **OrderType.Market**<br>- **OrderType.MIT**<br>- **OrderType.StopMarket**<br>- **OrderType.StopLimit** |
| **orderEntry** | Possible values:<br>- **OrderEntry.Automated**<br>- **OrderEntry.Manual**<br>Allows setting the tag for orders submitted manually or via automated trading logic (CME tag 1028). |
| **timeInForce** | Possible values:<br>- **TimeInForce.Day**<br>- **TimeInForce.Gtc**<br>- **TimeInForce.Gtd**<br>- **TimeInForce.Ioc**<br>- **TimeInForce.Opg** |
| **quantity** | Order quantity |
| **limitPrice** | Order limit price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| **stopPrice** | Order stop price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| **oco** | A string representing the OCO ID used to link OCO orders together |
| **name** | A string representing the name of the order. Max 50 characters.<br>Note: If using ATM Strategy **StartAtmStrategy()**, this value MUST be "Entry" |
| **gtd** | A **DateTime** value to be used with **TimeInForce.Gtd** \- for all other cases you can pass in **Core.Globals.MaxDate** |
| **customOrder** | Custom order if it is being used |

## [Examples](https://developer.ninjatrader.com/docs/desktop/createorder\#examples)

```jsx-150469391 csharp
// Example code
Order stopOrder;
stopOrder = myAccount.CreateOrder(myInstrument, OrderAction.Sell, OrderType.StopMarket, OrderEntry.Automated, TimeInForce.Day, 1, 0, 1400, "myOCO", "stopOrder", Core.Globals.MaxDate, null);

myAccount.Submit(new[] { stopOrder });

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/createorder\#definition)

Creates an **Order** to be submitted via **Submit()**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/createorder\#syntax)

`CreateOrder(Instrument instrument, OrderAction action, OrderType orderType, OrderEntry orderEntry, TimeInForce timeInForce, int quantity, double limitPrice, double stopPrice, string oco, string name, DateTime gtd, CustomOrder customOrder)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/createorder\#parameters)

| **instrument** | Order instrument |
| **orderAction** | Possible values:<br>- **OrderAction.Buy**<br>- **OrderAction.BuyToCover**<br>- **OrderAction.Sell**<br>- **OrderAction.SellShort** |
| **orderType** | Possible values:<br>- **OrderType.Limit**<br>- **OrderType.Market**<br>- **OrderType.MIT**<br>- **OrderType.StopMarket**<br>- **OrderType.StopLimit** |
| **orderEntry** | Possible values:<br>- **OrderEntry.Automated**<br>- **OrderEntry.Manual**<br>Allows setting the tag for orders submitted manually or via automated trading logic (CME tag 1028). |
| **timeInForce** | Possible values:<br>- **TimeInForce.Day**<br>- **TimeInForce.Gtc**<br>- **TimeInForce.Gtd**<br>- **TimeInForce.Ioc**<br>- **TimeInForce.Opg** |
| **quantity** | Order quantity |
| **limitPrice** | Order limit price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| **stopPrice** | Order stop price. Use "0" should this parameter be irrelevant for the OrderType being submitted. |
| **oco** | A string representing the OCO ID used to link OCO orders together |
| **name** | A string representing the name of the order. Max 50 characters.<br>Note: If using ATM Strategy **StartAtmStrategy()**, this value MUST be "Entry" |
| **gtd** | A **DateTime** value to be used with **TimeInForce.Gtd** \- for all other cases you can pass in **Core.Globals.MaxDate** |
| **customOrder** | Custom order if it is being used |

## [Examples](https://developer.ninjatrader.com/docs/desktop/createorder\#examples)

```jsx-150469391 csharp
// Example code
Order stopOrder;
stopOrder = myAccount.CreateOrder(myInstrument, OrderAction.Sell, OrderType.StopMarket, OrderEntry.Automated, TimeInForce.Day, 1, 0, 1400, "myOCO", "stopOrder", Core.Globals.MaxDate, null);

myAccount.Submit(new[] { stopOrder });

```