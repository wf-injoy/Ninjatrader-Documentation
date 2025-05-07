## [Definition](https://developer.ninjatrader.com/docs/desktop/characterlimit\#definition)

Determines the maximum number of characters the social network allows. Signature, text, and links all contribute to this character count displayed on the share window.

A value of **int.MaxValue** determines no practical limit and will make the character count not appear on the Share window.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/characterlimit\#property-value)

A **int** value that represents the maximum number of characters the social network allows.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/characterlimit\#syntax)

`CharacterLimit`

## [Examples](https://developer.ninjatrader.com/docs/desktop/characterlimit\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        CharacterLimit = 280;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/characterlimit\#definition)

Determines the maximum number of characters the social network allows. Signature, text, and links all contribute to this character count displayed on the share window.

A value of **int.MaxValue** determines no practical limit and will make the character count not appear on the Share window.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/characterlimit\#property-value)

A **int** value that represents the maximum number of characters the social network allows.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/characterlimit\#syntax)

`CharacterLimit`

## [Examples](https://developer.ninjatrader.com/docs/desktop/characterlimit\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        CharacterLimit = 280;
    }
}

```