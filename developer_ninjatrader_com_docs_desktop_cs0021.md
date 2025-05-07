The following **CS0021** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0021\#error-code-explanation)

This is a common error when calling indicators methods. It occurs when an indicator is called without its required parameter arguments before accessing an indexed value.

To fix this error you will need to first pass to the indicator method all the necessary parameter arguments. You can do this with `()` after the indicator name. Please note that you will still need to pass an empty parameter argument list even if your indicator requires no arguments.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0021\#error-description-\#1)

Cannot apply indexing with **\[\]** to an expression of type **'method group'**

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0021\#examples)

### Example \#1

## Note

Erroneous Sample Code - **SMA** is an indicator and requires parameter arguments

```jsx-1168641291 csharp
double value = SMA[0];

```

## Note

Resolution Sample Code - **SMA()** properly called

```jsx-1168641291 csharp
double value = SMA(14)[0];

```

### Example \#2

## Note

Erroneous Sample Code - **EMA** is an indicator and requires parameter arguments

```jsx-1168641291 csharp
double maDelta = EMA[0] - EMA[1];

```

## Note

Resolution Sample Code - **SMA()** properly called with an overload method (one of several variations)

```jsx-1168641291 csharp
double maDelta = EMA(High, 14)[0] - EMA(High, 14)[1];

```

The following **CS0021** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0021\#error-code-explanation)

This is a common error when calling indicators methods. It occurs when an indicator is called without its required parameter arguments before accessing an indexed value.

To fix this error you will need to first pass to the indicator method all the necessary parameter arguments. You can do this with `()` after the indicator name. Please note that you will still need to pass an empty parameter argument list even if your indicator requires no arguments.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0021\#error-description-\#1)

Cannot apply indexing with **\[\]** to an expression of type **'method group'**

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0021\#examples)

### Example \#1

## Note

Erroneous Sample Code - **SMA** is an indicator and requires parameter arguments

```jsx-1168641291 csharp
double value = SMA[0];

```

## Note

Resolution Sample Code - **SMA()** properly called

```jsx-1168641291 csharp
double value = SMA(14)[0];

```

### Example \#2

## Note

Erroneous Sample Code - **EMA** is an indicator and requires parameter arguments

```jsx-1168641291 csharp
double maDelta = EMA[0] - EMA[1];

```

## Note

Resolution Sample Code - **SMA()** properly called with an overload method (one of several variations)

```jsx-1168641291 csharp
double maDelta = EMA(High, 14)[0] - EMA(High, 14)[1];

```