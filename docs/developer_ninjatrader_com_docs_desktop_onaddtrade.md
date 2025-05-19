## [Definition](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#definition)

This method is called as each trade is added. You would add any custom math you wanted to do here.

## Note

If your performance metric only needs to iterate through all trades at the end to perform its calculation and does not need to be calculated on each trade then using the **property approach** (On demand example) will have less of a performance impact.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#syntax)

`protected override void OnAddTrade(Cbi.Trade trade)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#examples)

```jsx-150469391 csharp

protected override void OnAddTrade(Cbi.Trade trade)
{
     Values[(int)Cbi.PerformanceUnit.Currency] += trade.ProfitCurrency;
     Values[(int)Cbi.PerformanceUnit.Percent]  += trade.ProfitPercent;
     Values[(int)Cbi.PerformanceUnit.Pips]     += trade.ProfitPips;
     Values[(int)Cbi.PerformanceUnit.Points]   += trade.ProfitPoints;
     Values[(int)Cbi.PerformanceUnit.Ticks]    += trade.ProfitTicks;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#definition)

This method is called as each trade is added. You would add any custom math you wanted to do here.

## Note

If your performance metric only needs to iterate through all trades at the end to perform its calculation and does not need to be calculated on each trade then using the **property approach** (On demand example) will have less of a performance impact.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#syntax)

`protected override void OnAddTrade(Cbi.Trade trade)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/onaddtrade\#examples)

```jsx-150469391 csharp

protected override void OnAddTrade(Cbi.Trade trade)
{
     Values[(int)Cbi.PerformanceUnit.Currency] += trade.ProfitCurrency;
     Values[(int)Cbi.PerformanceUnit.Percent]  += trade.ProfitPercent;
     Values[(int)Cbi.PerformanceUnit.Pips]     += trade.ProfitPips;
     Values[(int)Cbi.PerformanceUnit.Points]   += trade.ProfitPoints;
     Values[(int)Cbi.PerformanceUnit.Ticks]    += trade.ProfitTicks;
}

```