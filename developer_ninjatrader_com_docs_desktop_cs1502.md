The following CS1502 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-code-explanation)

This error can occur when you pass in incorrect parameter object types into a method such as an indicator.

Please check the overload methods for the proper parameter object types and pass in the proper object. You can check the overload methods with **NinjaScript** editor’s Intelliprompt when you call a method.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-description-\#1)

The best overloaded method match for ' **NinjaTrader.NinjaScript.StrategyBase.SetStopLoss**( **CalculationMode**, **double**)' has some invalid arguments

```jsx-150469391 csharp
// Erroneous Sample Code - Close is a Series<double> object type and is not a valid value to the SetStopLoss() method
SetStopLoss(CalculationMode.Price, Close);

// Resolution Sample Code - The SetStopLoss() method takes A **double** value so pass in Close[0]
SetStopLoss(CalculationMode.Price, Close[0]);

```

## [Error Description \#2](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-description-\#2)

The best overloaded method match for ' **NinjaTrader.Indicator.Indicator.SMA**( **NinjaTrader.NinjaScript.ISeries `<double>`**, **int**)' has some invalid arguments

```jsx-150469391 csharp
// Erroneous Sample Code - Using an integer when the first parameter should be a Series<double>
double myValue = SMA(5, 5);

// Resolution Sample Code - 'myValue' will take the value of the current bar's SMA
double myValue = SMA(Close, 5)[0];

```

The following CS1502 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-code-explanation)

This error can occur when you pass in incorrect parameter object types into a method such as an indicator.

Please check the overload methods for the proper parameter object types and pass in the proper object. You can check the overload methods with **NinjaScript** editor’s Intelliprompt when you call a method.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-description-\#1)

The best overloaded method match for ' **NinjaTrader.NinjaScript.StrategyBase.SetStopLoss**( **CalculationMode**, **double**)' has some invalid arguments

```jsx-150469391 csharp
// Erroneous Sample Code - Close is a Series<double> object type and is not a valid value to the SetStopLoss() method
SetStopLoss(CalculationMode.Price, Close);

// Resolution Sample Code - The SetStopLoss() method takes A **double** value so pass in Close[0]
SetStopLoss(CalculationMode.Price, Close[0]);

```

## [Error Description \#2](https://developer.ninjatrader.com/docs/desktop/cs1502\#error-description-\#2)

The best overloaded method match for ' **NinjaTrader.Indicator.Indicator.SMA**( **NinjaTrader.NinjaScript.ISeries `<double>`**, **int**)' has some invalid arguments

```jsx-150469391 csharp
// Erroneous Sample Code - Using an integer when the first parameter should be a Series<double>
double myValue = SMA(5, 5);

// Resolution Sample Code - 'myValue' will take the value of the current bar's SMA
double myValue = SMA(Close, 5)[0];

```