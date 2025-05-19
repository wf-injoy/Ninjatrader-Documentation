You can create an automated strategy that generates a trade signal that executes a NinjaTrader [ATM Strategy](https://ninjatrader.com/support/helpguides/nt8/atm_strategy.htm).

- ATM Strategies operate in real-time only and will not execute on historical data thus they can't be backtested

- Executions resulting from an ATM Strategy that is created from within a NinjaScript automated strategy will not plot on a chart during real-time operation

- Strategy set up parameters such as [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection), [EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling), [IsExitOnSessionCloseStrategy](https://developer.ninjatrader.com/docs/desktop/isexitonsessionclosestrategy) do not apply when calling the [AtmStrategyCreate()](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) method

- Executions from ATM Strategies will not have an impact on the hosting NinjaScript strategy position and PnL - the NinjaScript strategy hands off the execution aspects to the ATM, thus no monitoring via the regular NinjaScript strategy methods will take place (also applies to strategy performance tracking)

- ATM Strategy stop orders can either be StopMarket or StopLimit orders, depending on which type is defined in the ATM Strategy Template (Advanced Options) you call in the [AtmStrategyCreate()](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) method in your NinjaScript strategy. To make the distinction clear which is used, following a naming convention for the template name is highly suggested (i.e. AtmStrategyTemplate\_STPLMT)

- A general sample for calling ATM's is preinstalled with NinjaTrader under the 'SampleATMStrategy' script - for a script showing how to implement reversal type setups, please see [this link](http://www.ninjatrader.com/support/forum/local_links.php?action=jump&catid=8&id=866) to our online resources.


## [There is a Clear Line](https://developer.ninjatrader.com/docs/desktop/using_atm_strategies\#there-is-a-clear-line)

There is a clear line between a NinjaScript Strategy and an ATM Strategy. The use model for creating an ATM Strategy within a NinjaScript Strategy is when you want to programmatically monitor and generate an entry signal and then manualy manage the resulting open position via an ATM Strategy in one of NinjaTrader's order entry windows.

You can create an automated strategy that generates a trade signal that executes a NinjaTrader [ATM Strategy](https://ninjatrader.com/support/helpguides/nt8/atm_strategy.htm).

- ATM Strategies operate in real-time only and will not execute on historical data thus they can't be backtested

- Executions resulting from an ATM Strategy that is created from within a NinjaScript automated strategy will not plot on a chart during real-time operation

- Strategy set up parameters such as [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection), [EntryHandling](https://developer.ninjatrader.com/docs/desktop/entryhandling), [IsExitOnSessionCloseStrategy](https://developer.ninjatrader.com/docs/desktop/isexitonsessionclosestrategy) do not apply when calling the [AtmStrategyCreate()](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) method

- Executions from ATM Strategies will not have an impact on the hosting NinjaScript strategy position and PnL - the NinjaScript strategy hands off the execution aspects to the ATM, thus no monitoring via the regular NinjaScript strategy methods will take place (also applies to strategy performance tracking)

- ATM Strategy stop orders can either be StopMarket or StopLimit orders, depending on which type is defined in the ATM Strategy Template (Advanced Options) you call in the [AtmStrategyCreate()](https://developer.ninjatrader.com/docs/desktop/atmstrategycreate) method in your NinjaScript strategy. To make the distinction clear which is used, following a naming convention for the template name is highly suggested (i.e. AtmStrategyTemplate\_STPLMT)

- A general sample for calling ATM's is preinstalled with NinjaTrader under the 'SampleATMStrategy' script - for a script showing how to implement reversal type setups, please see [this link](http://www.ninjatrader.com/support/forum/local_links.php?action=jump&catid=8&id=866) to our online resources.


## [There is a Clear Line](https://developer.ninjatrader.com/docs/desktop/using_atm_strategies\#there-is-a-clear-line)

There is a clear line between a NinjaScript Strategy and an ATM Strategy. The use model for creating an ATM Strategy within a NinjaScript Strategy is when you want to programmatically monitor and generate an entry signal and then manualy manage the resulting open position via an ATM Strategy in one of NinjaTrader's order entry windows.