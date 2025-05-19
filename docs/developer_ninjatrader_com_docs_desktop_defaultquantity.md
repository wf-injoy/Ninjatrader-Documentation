## [Definition](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#definition)

An order size variable that can be set either programmatically or overridden via the Strategy that determines the quantity of an entry order.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#property-value)

An **int** value represents the number of contracts or shares to enter a position with. Default value is 1.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#syntax)

`DefaultQuantity`

## [Examples](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        DefaultQuantity = 1;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#definition)

An order size variable that can be set either programmatically or overridden via the Strategy that determines the quantity of an entry order.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#property-value)

An **int** value represents the number of contracts or shares to enter a position with. Default value is 1.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#syntax)

`DefaultQuantity`

## [Examples](https://developer.ninjatrader.com/docs/desktop/defaultquantity\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        DefaultQuantity = 1;
    }
}

```