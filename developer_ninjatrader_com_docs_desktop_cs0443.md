The following **CS0443** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0443\#error-code-explanation)

This error is most commonly invoked when no index value is used inside the indexing brackets.

Please ensure you place a value inside the '\[\]'.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0443\#error-description-\#1)

**Syntax error, value expected**

```jsx-150469391 csharp
// Erroneous Sample Code - Missing index value
double myValue = SMA(20)[];

// Resolution Sample Code - 'myValue' takes on the current bar's SMA(20) value
double myValue = SMA(20)[0];

```

The following **CS0443** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0443\#error-code-explanation)

This error is most commonly invoked when no index value is used inside the indexing brackets.

Please ensure you place a value inside the '\[\]'.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0443\#error-description-\#1)

**Syntax error, value expected**

```jsx-150469391 csharp
// Erroneous Sample Code - Missing index value
double myValue = SMA(20)[];

// Resolution Sample Code - 'myValue' takes on the current bar's SMA(20) value
double myValue = SMA(20)[0];

```