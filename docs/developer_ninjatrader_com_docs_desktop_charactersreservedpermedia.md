## [Definition](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#definition)

Sets the number of characters allowed when attaching an image to ensure that character count is properly calculated.

## Note

Social networks which limit the number of characters for each post, will have a defined number of characters that are reserved when an image or other media is attached.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#property-value)

A int value that represents the number of characters reserved when attaching an image or other media.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#syntax)

`CharactersReservedPerMedia`

## [Examples](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        CharactersReservedPerMedia = 40;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#definition)

Sets the number of characters allowed when attaching an image to ensure that character count is properly calculated.

## Note

Social networks which limit the number of characters for each post, will have a defined number of characters that are reserved when an image or other media is attached.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#property-value)

A int value that represents the number of characters reserved when attaching an image or other media.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#syntax)

`CharactersReservedPerMedia`

## [Examples](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        CharactersReservedPerMedia = 40;
    }
}

```