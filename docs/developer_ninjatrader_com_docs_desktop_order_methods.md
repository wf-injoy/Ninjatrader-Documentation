## [Order Methods Overview](https://developer.ninjatrader.com/docs/desktop/order_methods\#order-methods-overview)

NinjaScript provides several approaches you can use for order placement within your NinjaScript strategy. The main approaches can be categorized as a Managed approach and an Unmanaged approach.

## Note

You will not be able to mix and match the two approaches. If you decide to go with the Managed approach you will only be able to use the Managed order methods. If you decide to go with the Unmanaged approach you will only be able to use the Unmanaged order methods.

## [Managed](https://developer.ninjatrader.com/docs/desktop/order_methods\#managed)

The Managed approach offers you order methods that are wrapped with an invisible convenience layer that allows you to focus on your system's trading rules leaving the underlying mechanics of order management and the relationships between entry and exit orders and positions to NinjaTrader. The cost for having the convenience layer is that there are **[order handling rules](https://developer.ninjatrader.com/docs/desktop/managed_approach)** that must be followed to prevent order errors.

- **[Understanding the Managed approach](https://developer.ninjatrader.com/docs/desktop/managed_approach)**
- **[Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling)**
- **[CancelOrder()](https://developer.ninjatrader.com/docs/desktop/cancelorder)**
- **[EnterLong()](https://developer.ninjatrader.com/docs/desktop/enterlong)**
- **[EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit)**
- **[EnterLongMIT()](https://developer.ninjatrader.com/docs/desktop/enterlongmit)**
- **[EnterLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/enterlongstopmarket)**
- **[EnterLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/enterlongstoplimit)**
- **[EnterShort()](https://developer.ninjatrader.com/docs/desktop/entershort)**
- **[EnterShortLimit()](https://developer.ninjatrader.com/docs/desktop/entershortlimit)**
- **[EnterShortMIT()](https://developer.ninjatrader.com/docs/desktop/entershortmit)**
- **[EnterShortStopMarket()](https://developer.ninjatrader.com/docs/desktop/entershortstopmarket)**
- **[EnterShortStopLimit()](https://developer.ninjatrader.com/docs/desktop/entershortstoplimit)**
- **[ExitLong()](https://developer.ninjatrader.com/docs/desktop/exitlong)**
- **[ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit)**
- **[ExitLongMIT()](https://developer.ninjatrader.com/docs/desktop/exitlongmit)**
- **[ExitLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitlongstopmarket)**
- **[ExitLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitlongstoplimit)**
- **[ExitShort()](https://developer.ninjatrader.com/docs/desktop/exitshort)**
- **[ExitShortLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortlimit)**
- **[ExitShortMIT()](https://developer.ninjatrader.com/docs/desktop/exitshortmit)**
- **[ExitShortStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitshortstopmarket)**
- **[ExitShortStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortstoplimit)**
- **[GetRealtimeOrder()](https://developer.ninjatrader.com/docs/desktop/getrealtimeorder)**
- **[SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget)**
- **[SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss)**
- **[SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop)**
- **[SetParabolicStop()](https://developer.ninjatrader.com/docs/desktop/setparabolicstop)**

## [Unmanaged](https://developer.ninjatrader.com/docs/desktop/order_methods\#unmanaged)

The Unmanaged approach offers you more flexible order methods without the convenience layer. This means you are not restricted to any order handling rules besides those imposed by the brokerage/exchange. With such flexibility though, you will have to ensure to program your strategy to handle any and all issues that may arise with placing orders.

- **[Understanding the Unmanaged approach](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach)**
- **[CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder)**
- **[ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder)**
- **[GetRealtimeOrder()](https://developer.ninjatrader.com/docs/desktop/getrealtimeorder)**
- **[IgnoreOverfill](https://developer.ninjatrader.com/docs/desktop/ignoreoverfill)**
- **[IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged)**
- **[SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged)**

## [Order Methods Overview](https://developer.ninjatrader.com/docs/desktop/order_methods\#order-methods-overview)

NinjaScript provides several approaches you can use for order placement within your NinjaScript strategy. The main approaches can be categorized as a Managed approach and an Unmanaged approach.

## Note

You will not be able to mix and match the two approaches. If you decide to go with the Managed approach you will only be able to use the Managed order methods. If you decide to go with the Unmanaged approach you will only be able to use the Unmanaged order methods.

## [Managed](https://developer.ninjatrader.com/docs/desktop/order_methods\#managed)

The Managed approach offers you order methods that are wrapped with an invisible convenience layer that allows you to focus on your system's trading rules leaving the underlying mechanics of order management and the relationships between entry and exit orders and positions to NinjaTrader. The cost for having the convenience layer is that there are **[order handling rules](https://developer.ninjatrader.com/docs/desktop/managed_approach)** that must be followed to prevent order errors.

- **[Understanding the Managed approach](https://developer.ninjatrader.com/docs/desktop/managed_approach)**
- **[Advanced Order Handling](https://developer.ninjatrader.com/docs/desktop/advanced_order_handling)**
- **[CancelOrder()](https://developer.ninjatrader.com/docs/desktop/cancelorder)**
- **[EnterLong()](https://developer.ninjatrader.com/docs/desktop/enterlong)**
- **[EnterLongLimit()](https://developer.ninjatrader.com/docs/desktop/enterlonglimit)**
- **[EnterLongMIT()](https://developer.ninjatrader.com/docs/desktop/enterlongmit)**
- **[EnterLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/enterlongstopmarket)**
- **[EnterLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/enterlongstoplimit)**
- **[EnterShort()](https://developer.ninjatrader.com/docs/desktop/entershort)**
- **[EnterShortLimit()](https://developer.ninjatrader.com/docs/desktop/entershortlimit)**
- **[EnterShortMIT()](https://developer.ninjatrader.com/docs/desktop/entershortmit)**
- **[EnterShortStopMarket()](https://developer.ninjatrader.com/docs/desktop/entershortstopmarket)**
- **[EnterShortStopLimit()](https://developer.ninjatrader.com/docs/desktop/entershortstoplimit)**
- **[ExitLong()](https://developer.ninjatrader.com/docs/desktop/exitlong)**
- **[ExitLongLimit()](https://developer.ninjatrader.com/docs/desktop/exitlonglimit)**
- **[ExitLongMIT()](https://developer.ninjatrader.com/docs/desktop/exitlongmit)**
- **[ExitLongStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitlongstopmarket)**
- **[ExitLongStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitlongstoplimit)**
- **[ExitShort()](https://developer.ninjatrader.com/docs/desktop/exitshort)**
- **[ExitShortLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortlimit)**
- **[ExitShortMIT()](https://developer.ninjatrader.com/docs/desktop/exitshortmit)**
- **[ExitShortStopMarket()](https://developer.ninjatrader.com/docs/desktop/exitshortstopmarket)**
- **[ExitShortStopLimit()](https://developer.ninjatrader.com/docs/desktop/exitshortstoplimit)**
- **[GetRealtimeOrder()](https://developer.ninjatrader.com/docs/desktop/getrealtimeorder)**
- **[SetProfitTarget()](https://developer.ninjatrader.com/docs/desktop/setprofittarget)**
- **[SetStopLoss()](https://developer.ninjatrader.com/docs/desktop/setstoploss)**
- **[SetTrailStop()](https://developer.ninjatrader.com/docs/desktop/settrailstop)**
- **[SetParabolicStop()](https://developer.ninjatrader.com/docs/desktop/setparabolicstop)**

## [Unmanaged](https://developer.ninjatrader.com/docs/desktop/order_methods\#unmanaged)

The Unmanaged approach offers you more flexible order methods without the convenience layer. This means you are not restricted to any order handling rules besides those imposed by the brokerage/exchange. With such flexibility though, you will have to ensure to program your strategy to handle any and all issues that may arise with placing orders.

- **[Understanding the Unmanaged approach](https://developer.ninjatrader.com/docs/desktop/unmanaged_approach)**
- **[CancelOrder()](https://developer.ninjatrader.com/docs/desktop/unmanaged_cancelorder)**
- **[ChangeOrder()](https://developer.ninjatrader.com/docs/desktop/changeorder)**
- **[GetRealtimeOrder()](https://developer.ninjatrader.com/docs/desktop/getrealtimeorder)**
- **[IgnoreOverfill](https://developer.ninjatrader.com/docs/desktop/ignoreoverfill)**
- **[IsUnmanaged](https://developer.ninjatrader.com/docs/desktop/isunmanaged)**
- **[SubmitOrderUnmanaged()](https://developer.ninjatrader.com/docs/desktop/submitorderunmanaged)**