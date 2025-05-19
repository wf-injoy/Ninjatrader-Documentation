The following **CS1061** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error's code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1061\#error-code-explanation)

This error can occur when you try to use a method or access an exposed property that does not exist for your particular object.

Please check the methods and exposed property available for your particular object.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1061\#error-description-\#1)

**'NinjaTrader.Indicator.CurrentDayOHL'** does not contain a definition for **'CurentOpen'**

```jsx-150469391 csharp
// Erroneous Sample Code - CurrentDayOHL()’s property is 'CurrentOpen' not 'CurentOpen' (typo)**
double value = CurrentDayOHL().CurentOpen[0];

```

```jsx-150469391 csharp
// Resolution Sample Code - 'CurrentOpen' property available
double value = CurrentDayOHL().CurrentOpen[0];

```

The following **CS1061** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error's code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1061\#error-code-explanation)

This error can occur when you try to use a method or access an exposed property that does not exist for your particular object.

Please check the methods and exposed property available for your particular object.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1061\#error-description-\#1)

**'NinjaTrader.Indicator.CurrentDayOHL'** does not contain a definition for **'CurentOpen'**

```jsx-150469391 csharp
// Erroneous Sample Code - CurrentDayOHL()’s property is 'CurrentOpen' not 'CurentOpen' (typo)**
double value = CurrentDayOHL().CurentOpen[0];

```

```jsx-150469391 csharp
// Resolution Sample Code - 'CurrentOpen' property available
double value = CurrentDayOHL().CurrentOpen[0];

```