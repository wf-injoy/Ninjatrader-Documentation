## [Definition](https://developer.ninjatrader.com/docs/desktop/positions\#definition)

A collection of Position objects generated for the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/positions\#property-value)

An **Collection** of Position objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/positions\#syntax)

`Account.Positions`

`<account>.Positions`

## [Examples](https://developer.ninjatrader.com/docs/desktop/positions\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Find our Sim101 account
        lock (Account.All)
            myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");
    }

    if (State == State.DataLoaded)
    {
        lock (myAccount.Positions)
        {
            Print("Positions in State.DataLoaded:");

            foreach (Position position in myAccount.Positions)
            {
                Print(String.Format("Position: {0} at {1}", position.MarketPosition, position.AveragePrice));
            }
        }
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/positions\#definition)

A collection of Position objects generated for the specified account

## [Property Value](https://developer.ninjatrader.com/docs/desktop/positions\#property-value)

An **Collection** of Position objects

## [Syntax](https://developer.ninjatrader.com/docs/desktop/positions\#syntax)

`Account.Positions`

`<account>.Positions`

## [Examples](https://developer.ninjatrader.com/docs/desktop/positions\#examples)

```jsx-150469391 csharp
private Account myAccount;

protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Find our Sim101 account
        lock (Account.All)
            myAccount = Account.All.FirstOrDefault(a => a.Name == "Sim101");
    }

    if (State == State.DataLoaded)
    {
        lock (myAccount.Positions)
        {
            Print("Positions in State.DataLoaded:");

            foreach (Position position in myAccount.Positions)
            {
                Print(String.Format("Position: {0} at {1}", position.MarketPosition, position.AveragePrice));
            }
        }
    }
}

```