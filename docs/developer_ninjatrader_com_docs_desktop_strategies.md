## [Definition](https://developer.ninjatrader.com/docs/desktop/strategies\#definition)

A collection of **StrategyBase** objects generated for the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/strategies\#property-value)

An [Collection](https://msdn.microsoft.com/en-us/library/ms132397(v=vs.110).aspx) of **StrategyBase** objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/strategies\#syntax)

`<account>.Strategies`

## [Examples](https://developer.ninjatrader.com/docs/desktop/strategies\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    foreach (StrategyBase strategy in myAccount.Strategies)
    {
        Print(String.Format("Account status updated. {0} strategy applied with position {1}", strategy.Name, strategy.Position));
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/strategies\#definition)

A collection of **StrategyBase** objects generated for the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/strategies\#property-value)

An [Collection](https://msdn.microsoft.com/en-us/library/ms132397(v=vs.110).aspx) of **StrategyBase** objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/strategies\#syntax)

`<account>.Strategies`

## [Examples](https://developer.ninjatrader.com/docs/desktop/strategies\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Initialize myAccount
    }
}

private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
{
    foreach (StrategyBase strategy in myAccount.Strategies)
    {
        Print(String.Format("Account status updated. {0} strategy applied with position {1}", strategy.Name, strategy.Position));
    }
}

```