## [Definition](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#definition)

Determines if the drawing tool can be clicked on by the user.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#property-value)

A bool value which wen true if the drawing tool cannot not be interacted with by a user; otherwise false. Default is set to false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#syntax)

`IgnoresUserInput`

## [Examples](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
           IgnoresUserInput = true; // Set this to true to make the drawing object non-interactive
     }
     else if (State == State.Configure)
     {

     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#definition)

Determines if the drawing tool can be clicked on by the user.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#property-value)

A bool value which wen true if the drawing tool cannot not be interacted with by a user; otherwise false. Default is set to false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#syntax)

`IgnoresUserInput`

## [Examples](https://developer.ninjatrader.com/docs/desktop/ignoresuserinput\#examples)

```jsx-150469391 csharp

protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
           IgnoresUserInput = true; // Set this to true to make the drawing object non-interactive
     }
     else if (State == State.Configure)
     {

     }
}

```