## [Definition](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#definition)

An event driven method used for strategies which is called for each **AccountItem** update for the account on which the strategy is running.

## Note

**OnAccountItemUpdate()** will be called continually in real-time if a position exists on the account on which the strategy is running. This is to provide updates on the current Unrealized Profit and Loss and associated risk values.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#syntax)

You must override the method in your strategy with the following syntax:

`protected override void OnAccountItemUpdate(Account account, AccountItem accountItem, double value)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#method-parameters)

| **account** | The [Account](https://developer.ninjatrader.com/docs/desktop/account) updated |
| **accountItem** | The [AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem) updated |
| **value** | The value of the AccountItem updated |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#examples)

```jsx-150469391 csharp
protected override void OnAccountItemUpdate(Account account, AccountItem accountItem, double value)
{
   Print(string.Format("{0} {1} {2}", account.Name, accountItem, value));

   // output:
   // Sim101 BuyingPower 103962.5
   // Sim101 CashValue 103962.5
   // Sim101 GrossRealizedProfitLoss 3962.5
   // Sim101 RealizedProfitLoss 3962.5
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#definition)

An event driven method used for strategies which is called for each **AccountItem** update for the account on which the strategy is running.

## Note

**OnAccountItemUpdate()** will be called continually in real-time if a position exists on the account on which the strategy is running. This is to provide updates on the current Unrealized Profit and Loss and associated risk values.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#syntax)

You must override the method in your strategy with the following syntax:

`protected override void OnAccountItemUpdate(Account account, AccountItem accountItem, double value)`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#method-parameters)

| **account** | The [Account](https://developer.ninjatrader.com/docs/desktop/account) updated |
| **accountItem** | The [AccountItem](https://developer.ninjatrader.com/docs/desktop/accountitem) updated |
| **value** | The value of the AccountItem updated |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onaccountitemupdate\#examples)

```jsx-150469391 csharp
protected override void OnAccountItemUpdate(Account account, AccountItem accountItem, double value)
{
   Print(string.Format("{0} {1} {2}", account.Name, accountItem, value));

   // output:
   // Sim101 BuyingPower 103962.5
   // Sim101 CashValue 103962.5
   // Sim101 GrossRealizedProfitLoss 3962.5
   // Sim101 RealizedProfitLoss 3962.5
}

```