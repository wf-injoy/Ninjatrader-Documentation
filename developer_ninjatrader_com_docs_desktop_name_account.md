## [Definition](https://developer.ninjatrader.com/docs/desktop/name_account\#definition)

Indicates the name of the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/name_account\#property-value)

A **string** representing the name of the account

## [Syntax](https://developer.ninjatrader.com/docs/desktop/name_account\#syntax)

`<account>.Name`

## [Examples](https://developer.ninjatrader.com/docs/desktop/name_account\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
 if (State == State.SetDefaults)
 {
		 // Initialize myAccount
 }

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
	 // Print the name of each account updated
	 Print(String.Format("{0} account updated", myAccount.Name));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/name_account\#definition)

Indicates the name of the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/name_account\#property-value)

A **string** representing the name of the account

## [Syntax](https://developer.ninjatrader.com/docs/desktop/name_account\#syntax)

`<account>.Name`

## [Examples](https://developer.ninjatrader.com/docs/desktop/name_account\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
 if (State == State.SetDefaults)
 {
		 // Initialize myAccount
 }

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
	 // Print the name of each account updated
	 Print(String.Format("{0} account updated", myAccount.Name));
}

```