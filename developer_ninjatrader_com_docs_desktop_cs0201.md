The following **CS0201** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0201\#error-code-explanation)

This error can occur when you make a statement solely from an indicator or variable call.

You will need to do something with the value you called for the statement to be complete.

### Error Description \#1

Only assignment, call, increment, decrement, await and new object expressions can be used as a statement

## Note

Erroneous Sample Code - Statement that does nothing

```jsx-150469391 csharp
// Erroneous Sample Code - Statement that does nothing
SMA(5)[0];

```

## Note

Resolution Sample Code - 'currentSMA' takes on the current bar's SMA(5) value

```jsx-1168641291 csharp
double currentSMA = SMA(5)[0];

```

The following **CS0201** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0201\#error-code-explanation)

This error can occur when you make a statement solely from an indicator or variable call.

You will need to do something with the value you called for the statement to be complete.

### Error Description \#1

Only assignment, call, increment, decrement, await and new object expressions can be used as a statement

## Note

Erroneous Sample Code - Statement that does nothing

```jsx-150469391 csharp
// Erroneous Sample Code - Statement that does nothing
SMA(5)[0];

```

## Note

Resolution Sample Code - 'currentSMA' takes on the current bar's SMA(5) value

```jsx-1168641291 csharp
double currentSMA = SMA(5)[0];

```