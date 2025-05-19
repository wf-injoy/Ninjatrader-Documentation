## [Definition](https://developer.ninjatrader.com/docs/desktop/startbehavior\#definition)

Sets the start behavior of the strategy. See [Syncing Account Positions](https://ninjatrader.com/support/helpguides/nt8/?syncing_account_positions.htm) for more information.

## Note

In order to use **AdoptAccountPosition** you will need to first set [**IsAdoptAccountPositionAware**](https://developer.ninjatrader.com/docs/desktop/isadoptaccountpositionaware) to true. Please be sure that your strategy is specifically programmed in a manner that can accommodate account positions before using this mode.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/startbehavior\#property-value)

An enum value that determines how the strategy behaves; Default value is set to **StartBehavior.WaitUntilFlat**. Possible values are:

- **StartBehavior.AdoptAccountPosition**
- **StartBehavior.ImmediatelySubmit**
- **StartBehavior.ImmediatelySubmitSynchronizeAccount**
- **StartBehavior.WaitUntilFlat**
- **StartBehavior.WaitUntilFlatSynchronizeAccount**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/startbehavior\#syntax)

`StartBehavior`

## [Examples](https://developer.ninjatrader.com/docs/desktop/startbehavior\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         StartBehavior = StartBehavior.WaitUntilFlat;
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/startbehavior\#definition)

Sets the start behavior of the strategy. See [Syncing Account Positions](https://ninjatrader.com/support/helpguides/nt8/?syncing_account_positions.htm) for more information.

## Note

In order to use **AdoptAccountPosition** you will need to first set [**IsAdoptAccountPositionAware**](https://developer.ninjatrader.com/docs/desktop/isadoptaccountpositionaware) to true. Please be sure that your strategy is specifically programmed in a manner that can accommodate account positions before using this mode.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/startbehavior\#property-value)

An enum value that determines how the strategy behaves; Default value is set to **StartBehavior.WaitUntilFlat**. Possible values are:

- **StartBehavior.AdoptAccountPosition**
- **StartBehavior.ImmediatelySubmit**
- **StartBehavior.ImmediatelySubmitSynchronizeAccount**
- **StartBehavior.WaitUntilFlat**
- **StartBehavior.WaitUntilFlatSynchronizeAccount**

## [Syntax](https://developer.ninjatrader.com/docs/desktop/startbehavior\#syntax)

`StartBehavior`

## [Examples](https://developer.ninjatrader.com/docs/desktop/startbehavior\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         StartBehavior = StartBehavior.WaitUntilFlat;
     }
}

```