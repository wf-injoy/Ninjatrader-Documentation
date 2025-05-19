## [Definition](https://developer.ninjatrader.com/docs/desktop/get\#definition)

Returns the value of an **AccountItem**, such as **BuyingPower**, **CashVal**, etc.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/get\#method-return-value)

A double representing the value of the requested **AccountItem**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/get\#syntax)

`Get(AccountItem itemType, Cbi.Currency currency)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/get\#parameters)

| **itemType** | The desired **AccountItem** to return |
| **Currency** | The account currency the value should be denoted (required parameter, but has no effect on returned value) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/get\#examples)

```jsx-150469391 csharp
// Evaluates to see if the account has more than $25000
if (Account.Get(AccountItem.CashValue, Currency.UsDollar) > 25000)
{
   // Do something;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/get\#definition)

Returns the value of an **AccountItem**, such as **BuyingPower**, **CashVal**, etc.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/get\#method-return-value)

A double representing the value of the requested **AccountItem**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/get\#syntax)

`Get(AccountItem itemType, Cbi.Currency currency)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/get\#parameters)

| **itemType** | The desired **AccountItem** to return |
| **Currency** | The account currency the value should be denoted (required parameter, but has no effect on returned value) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/get\#examples)

```jsx-150469391 csharp
// Evaluates to see if the account has more than $25000
if (Account.Get(AccountItem.CashValue, Currency.UsDollar) > 25000)
{
   // Do something;
}

```