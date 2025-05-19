## [Understanding How Orders are backfilled for **NinjaScript** strategies](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#understanding-how-orders-are-backfilled-for-strategies)

**NinjaScript** strategies use an algorithm to process order fills on historical data in two scenarios: when processing fills in the Strategy Analyzer, or when processing historical orders for a live running strategy. The algorithm fills historical orders using the same set of logic in both scenarios. Below is an outline of the logic used to determine the appropriate fill price for each historical order. When more than one order needs to be filled at once, the logic below will be ran for each individual order in succession.

## [General Outline](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#general-outline)

The steps involved in determining the appropriate fill price for an order are documented in their own sections below. The general, top-level outline of the logic can be broken into three steps:

1. Prepare to calculate fill prices
2. Take three passes to calculate the appropriate fill price for each order which needs filled
3. Fill the orders using the calculated fill price

## [Step 1 - Prepare to Calculate Fill Prices](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-1---prepare-to-calculate-fill-prices)

1. Determine all orders that need filled
2. Determine the current bar being formed at the time
3. Determine whether the current bar's first move was upward or downward
4. Determine the strategy being run
5. Determine the [Bars In Progress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) the strategy is currently processing

## [Step 2 - Take Three Passes To Determine Fill Price](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-2---take-three-passes-to-determine-fill-price)

The bulk of the backfill logic takes place in this step. Here orders are tested for their order types and prices, and are compared against current bar data to determine the appropriate fill prices per order type in different scenarios.

## Note

Throughout these three passes, prices are temporarily stored in two variables: a "next high price" and a "next low price." These are used to approximate the price that would be hit on the next tick, for the purpose of setting the fill price.

### 1\. **First Pass**

a. If the current bar moved up first, save the current bar high price as the "next high price," then save the current bar Open price as the "next low price."

i. If it moved down first, save the current bar Open price as the "next high price," then save the current bar Low price as the "next low price."

b. If it's a Market Buy order, set the fill price to the lesser of the "next high price" or the bar Open.

i. If it's a Market Sell order, set the fill price to the greater of the "next high price" or the bar Open.

c. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set the fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the saved "next low price" or the current bar Open, taking slippage into account.

d. Handle the special case of Limit orders with "Fill Limit Orders on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

e. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price value or the current order's Limit price.

2. If it is Short, set the fill price to the lesser of the existing fill price value or the current order's Limit price.


### 2\. **Second Pass**

a. If the current bar moved up first, save the current bar High price as the "next high price," then save the current bar Low price as the "next low price."

i. If it moved down first, save the current bar Low price as the "next high price," then save the current bar Low price as the "next low price."

b. If it's a Market Buy order and the bar moved up first, set the fill price to the lesser of the "next high price" or the bar High.

i. If the bar moved down first, set the fill price to the lesser of the "next high price" or the bar Low.

c. If it's a Market Sell order and the bar moved up first, set the fill price to the greater of the "next high price" or the bar High.

i. If the bar moved down first, set the fill price to the greater of the "next high price" or the bar Low.

d. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the "next low price" or the current bar Open, taking slippage into account.

e. Handle the special case of Limit orders with "Fill Limit on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

f. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price value or the current order's Limit price.

2. If the order is Short, set the fill price to the lesser of the existing fill price or the current order's Limit price.


### 3\. **Third Pass**

a. If the current bar moved up first, save the current bar Close price as the "next high price," then save the current bar Low price as the "next low price."

i. If it moved down first, save the current bar High price as the "next high price," then save the current bar Close price as the "next low price."

b. If it's a Market Buy order and the bar moved up first, set the fill price to the lesser of the "next high price" or the bar Low.

i. If the bar moved down first, set the fill price to the lesser of the "next high price" or the bar High.

c. If it's a Market Sell order and the bar moved up first, set the fill price to the greater of the "next high price" or the bar Low.

i. If the bar moved down first, set the fill price to the greater of the "next high price" or the bar High.

d. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set the fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the "next low price" or the current bar Open, taking slippage into account.

e. Handle the special case of Limit orders with "Fill Limit on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

f. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price or the current order's Limit price.

2. If the order is Short, set the fill price to the lesser of the existing fill price or the current order's Limit price.


## [Step 3 - Fill the Order](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-3---fill-the-order)

Each order is filled using the final fill price calculated for that particular order. If an order cannot be filled at this step, no further attempts will be made. Possible scenarios which would cause an order not to be filled at this stage include switching from **State.Historical** to **State.Realtime** when the strategy is currently waiting for a flat position before submitting orders, or a connectivity issue.

1. If the order is an entry, first temporarily clear all Entry Signals and pending orders from internally held collections of pending Entry Signals and orders.

2. If its an exit, first determine the quantity that needs to be filled.

a. If the position being closed has not been partially closed already, use the full order quantity.

b. If the position has already been partially closed by other orders, set the order quantity to the remaining position quantity.

3. Determine whether the strategy needs to wait until flat before filling the order.

a. This would apply if an exit order is being processed in real time, attempting to exit a position that was simulated on historical data.

4. Create and parameterize a new Execution object (set Account, Commission, Instrument, Name, etc.).

5. Set properties of the Order object being analyzed.

a. AvgFillPrice, Filled (quantity), OrderState (set to **OrderState.Filled**).

6. Add the new Execution to the Executions collection.

7. Add the order to the Orders collection.

8. Fill the order.


## [Understanding How Orders are backfilled for **NinjaScript** strategies](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#understanding-how-orders-are-backfilled-for-strategies)

**NinjaScript** strategies use an algorithm to process order fills on historical data in two scenarios: when processing fills in the Strategy Analyzer, or when processing historical orders for a live running strategy. The algorithm fills historical orders using the same set of logic in both scenarios. Below is an outline of the logic used to determine the appropriate fill price for each historical order. When more than one order needs to be filled at once, the logic below will be ran for each individual order in succession.

## [General Outline](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#general-outline)

The steps involved in determining the appropriate fill price for an order are documented in their own sections below. The general, top-level outline of the logic can be broken into three steps:

1. Prepare to calculate fill prices
2. Take three passes to calculate the appropriate fill price for each order which needs filled
3. Fill the orders using the calculated fill price

## [Step 1 - Prepare to Calculate Fill Prices](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-1---prepare-to-calculate-fill-prices)

1. Determine all orders that need filled
2. Determine the current bar being formed at the time
3. Determine whether the current bar's first move was upward or downward
4. Determine the strategy being run
5. Determine the [Bars In Progress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) the strategy is currently processing

## [Step 2 - Take Three Passes To Determine Fill Price](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-2---take-three-passes-to-determine-fill-price)

The bulk of the backfill logic takes place in this step. Here orders are tested for their order types and prices, and are compared against current bar data to determine the appropriate fill prices per order type in different scenarios.

## Note

Throughout these three passes, prices are temporarily stored in two variables: a "next high price" and a "next low price." These are used to approximate the price that would be hit on the next tick, for the purpose of setting the fill price.

### 1\. **First Pass**

a. If the current bar moved up first, save the current bar high price as the "next high price," then save the current bar Open price as the "next low price."

i. If it moved down first, save the current bar Open price as the "next high price," then save the current bar Low price as the "next low price."

b. If it's a Market Buy order, set the fill price to the lesser of the "next high price" or the bar Open.

i. If it's a Market Sell order, set the fill price to the greater of the "next high price" or the bar Open.

c. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set the fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the saved "next low price" or the current bar Open, taking slippage into account.

d. Handle the special case of Limit orders with "Fill Limit Orders on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

e. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price value or the current order's Limit price.

2. If it is Short, set the fill price to the lesser of the existing fill price value or the current order's Limit price.


### 2\. **Second Pass**

a. If the current bar moved up first, save the current bar High price as the "next high price," then save the current bar Low price as the "next low price."

i. If it moved down first, save the current bar Low price as the "next high price," then save the current bar Low price as the "next low price."

b. If it's a Market Buy order and the bar moved up first, set the fill price to the lesser of the "next high price" or the bar High.

i. If the bar moved down first, set the fill price to the lesser of the "next high price" or the bar Low.

c. If it's a Market Sell order and the bar moved up first, set the fill price to the greater of the "next high price" or the bar High.

i. If the bar moved down first, set the fill price to the greater of the "next high price" or the bar Low.

d. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the "next low price" or the current bar Open, taking slippage into account.

e. Handle the special case of Limit orders with "Fill Limit on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

f. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price value or the current order's Limit price.

2. If the order is Short, set the fill price to the lesser of the existing fill price or the current order's Limit price.


### 3\. **Third Pass**

a. If the current bar moved up first, save the current bar Close price as the "next high price," then save the current bar Low price as the "next low price."

i. If it moved down first, save the current bar High price as the "next high price," then save the current bar Close price as the "next low price."

b. If it's a Market Buy order and the bar moved up first, set the fill price to the lesser of the "next high price" or the bar Low.

i. If the bar moved down first, set the fill price to the lesser of the "next high price" or the bar High.

c. If it's a Market Sell order and the bar moved up first, set the fill price to the greater of the "next high price" or the bar Low.

i. If the bar moved down first, set the fill price to the greater of the "next high price" or the bar High.

d. Ensure the strategy is currently processing the bar series on which the order resides, then:

i. If the current order is Long, set the fill price to the lesser of the "next high price" or the current bar Open, taking slippage into account.

1. If it is Short, set the fill price to the greater of the "next low price" or the current bar Open, taking slippage into account.

e. Handle the special case of Limit orders with "Fill Limit on Touch" enabled.

i. If the limit price has been touched, set the fill price to current bar Open.

f. Ensure the order would be filled without errors by comparing its stop and/or limit prices against each other and the current bar, then:

i. For Limit orders, set the fill price to the current order's Limit price (however this is 'clamped' to happen inside the bar though).

ii. For Stop Limit orders:

1. If the order is Long, set the fill price to the greater of the existing fill price or the current order's Limit price.

2. If the order is Short, set the fill price to the lesser of the existing fill price or the current order's Limit price.


## [Step 3 - Fill the Order](https://developer.ninjatrader.com/docs/desktop/historical_order_backfill_logic\#step-3---fill-the-order)

Each order is filled using the final fill price calculated for that particular order. If an order cannot be filled at this step, no further attempts will be made. Possible scenarios which would cause an order not to be filled at this stage include switching from **State.Historical** to **State.Realtime** when the strategy is currently waiting for a flat position before submitting orders, or a connectivity issue.

1. If the order is an entry, first temporarily clear all Entry Signals and pending orders from internally held collections of pending Entry Signals and orders.

2. If its an exit, first determine the quantity that needs to be filled.

a. If the position being closed has not been partially closed already, use the full order quantity.

b. If the position has already been partially closed by other orders, set the order quantity to the remaining position quantity.

3. Determine whether the strategy needs to wait until flat before filling the order.

a. This would apply if an exit order is being processed in real time, attempting to exit a position that was simulated on historical data.

4. Create and parameterize a new Execution object (set Account, Commission, Instrument, Name, etc.).

5. Set properties of the Order object being analyzed.

a. AvgFillPrice, Filled (quantity), OrderState (set to **OrderState.Filled**).

6. Add the new Execution to the Executions collection.

7. Add the order to the Orders collection.

8. Fill the order.