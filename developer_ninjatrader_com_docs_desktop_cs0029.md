The following **CS0029** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-code-explanation)

This error can occur when you try to convert from one **type** to another **type**.

To fix this error, ensure that you are assigning the correct value type.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#1)

Cannot implicitly convert type ' **int**' to ' **bool**'

```jsx-150469391 csharp
// Erroneous Sample Code - 'CurrentBar' is an integer
if (CurrentBar)

```

```jsx-150469391 csharp
// Resolution Sample Code - Compares an integer with another integer
if (CurrentBar < 1)

```

## [Error Description \#2](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#2)

Cannot implicitly convert type ' **double**' to ' **bool**'

```jsx-150469391 csharp
// Erroneous Sample Code – Close[0] returns A **double** value
if (Close[0])

```

```jsx-150469391 csharp
// Resolution Sample Code – Compares a double with another double
if (Close[0] > Close[1])

```

## [Error Description \#3](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#3)

Cannot implicitly convert type ' **NinjaTrader.NinjaScript.Indicators.SMA**' to ' **double**'

```jsx-150469391 csharp
// Erroneous Sample Code - Incorrect since assigning an indicator to a variable of double type
double myValue = SMA(20);

```

```jsx-150469391 csharp
// Resolution Sample Code - Correct expression since we are accessing the current bar's value of the SMA indicator
double myValue = SMA(20)[0];

```

The following **CS0029** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-code-explanation)

This error can occur when you try to convert from one **type** to another **type**.

To fix this error, ensure that you are assigning the correct value type.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#1)

Cannot implicitly convert type ' **int**' to ' **bool**'

```jsx-150469391 csharp
// Erroneous Sample Code - 'CurrentBar' is an integer
if (CurrentBar)

```

```jsx-150469391 csharp
// Resolution Sample Code - Compares an integer with another integer
if (CurrentBar < 1)

```

## [Error Description \#2](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#2)

Cannot implicitly convert type ' **double**' to ' **bool**'

```jsx-150469391 csharp
// Erroneous Sample Code – Close[0] returns A **double** value
if (Close[0])

```

```jsx-150469391 csharp
// Resolution Sample Code – Compares a double with another double
if (Close[0] > Close[1])

```

## [Error Description \#3](https://developer.ninjatrader.com/docs/desktop/cs0029\#error-description-\#3)

Cannot implicitly convert type ' **NinjaTrader.NinjaScript.Indicators.SMA**' to ' **double**'

```jsx-150469391 csharp
// Erroneous Sample Code - Incorrect since assigning an indicator to a variable of double type
double myValue = SMA(20);

```

```jsx-150469391 csharp
// Resolution Sample Code - Correct expression since we are accessing the current bar's value of the SMA indicator
double myValue = SMA(20)[0];

```