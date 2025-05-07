## [Definition](https://developer.ninjatrader.com/docs/desktop/connection\#definition)

Indicates the data connection used for the specified account.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/connection\#property-value)

An instance of the **Connection** class containing information about the connection used for a specified account.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/connection\#syntax)

`<account>.Connection`

## [Examples](https://developer.ninjatrader.com/docs/desktop/connection\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    Print(String.Format("{0} connection updated", myAccount.Connection.Options.Name));
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/connection\#definition)

Indicates the data connection used for the specified account.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/connection\#property-value)

An instance of the **Connection** class containing information about the connection used for a specified account.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/connection\#syntax)

`<account>.Connection`

## [Examples](https://developer.ninjatrader.com/docs/desktop/connection\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    Print(String.Format("{0} connection updated", myAccount.Connection.Options.Name));
}

```