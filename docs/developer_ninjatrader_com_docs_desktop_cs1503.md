## [CS1503](https://developer.ninjatrader.com/docs/desktop/cs1503\#cs1503)

The following CS1503 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

### Error Description \#1

Cannot implicitly convert type from 'string' to 'double'

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot pass in a string to a Series<double>
Value[0] = "Close[0]";

```

```jsx-150469391 csharp
// Resolution Sample Code - Sets Series<double> to the current bar's Close value
Value[0] = Close[0];

```

### Error Description \#2

Cannot implicitly convert type 'NinjaTrader.NinjaScript.Indicators.SMA' to 'double'

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot pass in a Series<double> object to a Series<double> Set() method
Values[0] = SMA(20);

```

```jsx-150469391 csharp
// Resolution Sample Code - Sets Series<double> to the current bar's SMA(20) value
Values[0] = SMA(20)[0];

```

## [CS1503](https://developer.ninjatrader.com/docs/desktop/cs1503\#cs1503)

The following CS1503 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

### Error Description \#1

Cannot implicitly convert type from 'string' to 'double'

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot pass in a string to a Series<double>
Value[0] = "Close[0]";

```

```jsx-150469391 csharp
// Resolution Sample Code - Sets Series<double> to the current bar's Close value
Value[0] = Close[0];

```

### Error Description \#2

Cannot implicitly convert type 'NinjaTrader.NinjaScript.Indicators.SMA' to 'double'

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot pass in a Series<double> object to a Series<double> Set() method
Values[0] = SMA(20);

```

```jsx-150469391 csharp
// Resolution Sample Code - Sets Series<double> to the current bar's SMA(20) value
Values[0] = SMA(20)[0];

```