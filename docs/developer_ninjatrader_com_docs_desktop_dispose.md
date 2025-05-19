## [Definition](https://developer.ninjatrader.com/docs/desktop/dispose\#definition)

Releases any device resources used for the drawing tool.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/dispose\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/dispose\#syntax)

`Dispose()`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/dispose\#method-parameters)

This method does not accept any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/dispose\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name                 = @"My Drawing Tool";
   }

   else if (State == State.Terminated)
     Dispose();
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/dispose\#definition)

Releases any device resources used for the drawing tool.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/dispose\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/dispose\#syntax)

`Dispose()`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/dispose\#method-parameters)

This method does not accept any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/dispose\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
     Name                 = @"My Drawing Tool";
   }

   else if (State == State.Terminated)
     Dispose();
}

```