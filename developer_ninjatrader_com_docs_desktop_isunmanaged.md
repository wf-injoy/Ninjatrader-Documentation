## [Definition](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#definition)

Determines if the strategy will be using Unmanaged order methods.

## Note

Unmanaged order methods and **Managed order methods** cannot be used interchangeably. When **IsUnmanaged** is set to true, calling managed order methods such as **EnterLong()**, **SetStopLoss()**, etc., will generate an error which will be displayed on the **Log tab** of the Control Center.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#property-value)

This property returns true if the strategy will use Unmanaged order methods; otherwise, false. Default is set to false.

## Warning

Warning: This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#syntax)

`IsUnmanaged`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Use Unmanaged order methods
        IsUnmanaged = true;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#definition)

Determines if the strategy will be using Unmanaged order methods.

## Note

Unmanaged order methods and **Managed order methods** cannot be used interchangeably. When **IsUnmanaged** is set to true, calling managed order methods such as **EnterLong()**, **SetStopLoss()**, etc., will generate an error which will be displayed on the **Log tab** of the Control Center.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#property-value)

This property returns true if the strategy will use Unmanaged order methods; otherwise, false. Default is set to false.

## Warning

Warning: This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#syntax)

`IsUnmanaged`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isunmanaged\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Use Unmanaged order methods
        IsUnmanaged = true;
    }
}

```