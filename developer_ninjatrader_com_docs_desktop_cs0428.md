The following **CS0428** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0428\#error-code-explanation)

This error can occur when you miscall a method such as indicator methods.

If you are calling an indicator please ensure that you have both the parameters '()' and the indexing value '\[\]' set. For other methods please ensure you pass all required parameters through the parameters set '()'.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0428\#error-description-\#1)

**Cannot convert method group 'SMA' to non-delegate type 'double'. Did you intend to invoke the method?**

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0428\#examples)

### Example \#1

```jsx-150469391 csharp
// Erroneous Sample Code - SMA() indicator method is improperly called
double myValue = SMA;

```

```jsx-150469391 csharp
// Resolution Sample Code - SMA() indicator method is properly called
double myValue = SMA(5)[0];

```

### Example \#2

```jsx-150469391 csharp
// Erroneous Sample Code - ToString is a method and requires round brackets () to be properly called
string str = Close[5].ToString;

```

```jsx-150469391 csharp
// Resolution Sample Code - ToString() is properly called
string str = Close[5].ToString();

```

The following **CS0428** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0428\#error-code-explanation)

This error can occur when you miscall a method such as indicator methods.

If you are calling an indicator please ensure that you have both the parameters '()' and the indexing value '\[\]' set. For other methods please ensure you pass all required parameters through the parameters set '()'.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0428\#error-description-\#1)

**Cannot convert method group 'SMA' to non-delegate type 'double'. Did you intend to invoke the method?**

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0428\#examples)

### Example \#1

```jsx-150469391 csharp
// Erroneous Sample Code - SMA() indicator method is improperly called
double myValue = SMA;

```

```jsx-150469391 csharp
// Resolution Sample Code - SMA() indicator method is properly called
double myValue = SMA(5)[0];

```

### Example \#2

```jsx-150469391 csharp
// Erroneous Sample Code - ToString is a method and requires round brackets () to be properly called
string str = Close[5].ToString;

```

```jsx-150469391 csharp
// Resolution Sample Code - ToString() is properly called
string str = Close[5].ToString();

```