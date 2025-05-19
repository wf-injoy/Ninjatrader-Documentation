The following CS1501 error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1501\#error-code-explanation)

This error can occur when you use an overload (method parameter signature) that does not exist. This could be because you are passing in 3 arguments when the method only requires 2.

You can cycle through the available overloads with the use of the up and down arrows on the **Intelliprompt** when you call an indicator method or any other method.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1501\#error-description-\#1)

No overload for method ' **SMA**' takes '0' arguments

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs1501\#examples)

### Example \#1

## Note

Erroneous Sample Code - **SMA()** does not contain an overload that has 3 arguments

```jsx-1168641291 csharp
double myValue = SMA(Close, 5, 2)[0];

```

## Note

Resolution Sample Code - **SMA()** has an overload consisting of 2 arguments

```jsx-1168641291 csharp
double myValue = SMA(Close, 5)[0];

```

### Example \#2

## Note

Erroneous Sample Code - **EMA()** does not contain an overload that has 0 arguments

```jsx-1168641291 csharp
double myValue = EMA()[0];

```

## Note

Resolution Sample Code - **EMA()** has an overload consisting of 1 argument

```jsx-1168641291 csharp
double myValue = EMA(5)[0];

```

The following CS1501 error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1501\#error-code-explanation)

This error can occur when you use an overload (method parameter signature) that does not exist. This could be because you are passing in 3 arguments when the method only requires 2.

You can cycle through the available overloads with the use of the up and down arrows on the **Intelliprompt** when you call an indicator method or any other method.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1501\#error-description-\#1)

No overload for method ' **SMA**' takes '0' arguments

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs1501\#examples)

### Example \#1

## Note

Erroneous Sample Code - **SMA()** does not contain an overload that has 3 arguments

```jsx-1168641291 csharp
double myValue = SMA(Close, 5, 2)[0];

```

## Note

Resolution Sample Code - **SMA()** has an overload consisting of 2 arguments

```jsx-1168641291 csharp
double myValue = SMA(Close, 5)[0];

```

### Example \#2

## Note

Erroneous Sample Code - **EMA()** does not contain an overload that has 0 arguments

```jsx-1168641291 csharp
double myValue = EMA()[0];

```

## Note

Resolution Sample Code - **EMA()** has an overload consisting of 1 argument

```jsx-1168641291 csharp
double myValue = EMA(5)[0];

```