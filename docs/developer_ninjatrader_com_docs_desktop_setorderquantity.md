## [Definition](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#definition)

Determines how order sizes are calculated for a given strategy.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#property-value)

An enum determining how order quantities are set. Default value is set to **SetOrderQuantity.Strategy**.

Possible values are:

| Property | Description |
| --- | --- |
| **SetOrderQuantity.DefaultQuantity** | User defined order size based on the [DefaultQuantity](https://developer.ninjatrader.com/docs/desktop/defaultquantity) property |
| **SetOrderQuantity.Strategy** | Takes the order size specified programmatically within the strategy |

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#syntax)

`SetOrderQuantity`

## [Examples](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         SetOrderQuantity = SetOrderQuantity.DefaultQuantity; // calculate orders based off default size
     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#definition)

Determines how order sizes are calculated for a given strategy.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#property-value)

An enum determining how order quantities are set. Default value is set to **SetOrderQuantity.Strategy**.

Possible values are:

| Property | Description |
| --- | --- |
| **SetOrderQuantity.DefaultQuantity** | User defined order size based on the [DefaultQuantity](https://developer.ninjatrader.com/docs/desktop/defaultquantity) property |
| **SetOrderQuantity.Strategy** | Takes the order size specified programmatically within the strategy |

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#syntax)

`SetOrderQuantity`

## [Examples](https://developer.ninjatrader.com/docs/desktop/setorderquantity\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.Configure)
     {
         SetOrderQuantity = SetOrderQuantity.DefaultQuantity; // calculate orders based off default size
     }
}

```