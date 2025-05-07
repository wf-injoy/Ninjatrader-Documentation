## [Definition](https://developer.ninjatrader.com/docs/desktop/useoauth\#definition)

If this property is set to true, a Connect button will appear in the dialogue for configuring the adapter that will call **OnAuthorizeAccount()** when the user clicks it.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/useoauth\#property-value)

A bool value determining if the **OnAuthorizeAccount()** method should be called in order to authorize the account to the social service.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/useoauth\#syntax)

`UseOAuth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/useoauth\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      UseOAuth = true;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/useoauth\#definition)

If this property is set to true, a Connect button will appear in the dialogue for configuring the adapter that will call **OnAuthorizeAccount()** when the user clicks it.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/useoauth\#property-value)

A bool value determining if the **OnAuthorizeAccount()** method should be called in order to authorize the account to the social service.

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/useoauth\#syntax)

`UseOAuth`

## [Examples](https://developer.ninjatrader.com/docs/desktop/useoauth\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      UseOAuth = true;
   }
}

```