The following **CS1525** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1525\#error-code-explanation)

The compiler detected an invalid character in an expression.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1525\#error-description-\#1)

{ expected

### Erroneous Sample Code - If statement is not opened

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if(IsFirstTickOfBar)
}

```

### Resolution Sample Code - If statement is open and closed

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar)
   {
     // do something
   }
}

```

The following **CS1525** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1525\#error-code-explanation)

The compiler detected an invalid character in an expression.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1525\#error-description-\#1)

{ expected

### Erroneous Sample Code - If statement is not opened

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if(IsFirstTickOfBar)
}

```

### Resolution Sample Code - If statement is open and closed

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   if (IsFirstTickOfBar)
   {
     // do something
   }
}

```