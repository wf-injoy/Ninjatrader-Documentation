The following CS0200 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0200\#error-code-explanation)

This error is most common when you try to assign values to a particular **Series `<t>`** index that is read-only. Instead try making your own [Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) and assign the value there.

## [Error Description](https://developer.ninjatrader.com/docs/desktop/cs0200\#error-description)

Property or indexer ' **NinjaTrader.NinjaScript.ISeries `<double>`.this\[int\]**' cannot be assigned to -- it is read only

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0200\#examples)

### Example \#1

## Note

Erroneous Sample Code - Cannot assign values to something that is read-only

```jsx-1168641291 csharp
Close[0] = 25;

```

## Note

Resolution Sample Code - Assigns value to a custom Series< `double` >

```jsx-1168641291 csharp
myCustomClose[0] = 25;

```

### Example \#2

## Note

Erroneous Sample Code - Cannot reassign values to Series< `double` \> indexed value and cannot have an if statement based on an assignment operator

```jsx-1168641291 csharp
if (Close[0] = Open[0])

```

## Note

Resolution Sample Code - Properly compares two Series< `double` \> values

```jsx-1168641291 csharp
if (Close[0] == Open[0])

```

The following CS0200 error code information is provided within the context of NinjaScript. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0200\#error-code-explanation)

This error is most common when you try to assign values to a particular **Series `<t>`** index that is read-only. Instead try making your own [Series< `t` >](https://developer.ninjatrader.com/docs/desktop/seriest) and assign the value there.

## [Error Description](https://developer.ninjatrader.com/docs/desktop/cs0200\#error-description)

Property or indexer ' **NinjaTrader.NinjaScript.ISeries `<double>`.this\[int\]**' cannot be assigned to -- it is read only

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0200\#examples)

### Example \#1

## Note

Erroneous Sample Code - Cannot assign values to something that is read-only

```jsx-1168641291 csharp
Close[0] = 25;

```

## Note

Resolution Sample Code - Assigns value to a custom Series< `double` >

```jsx-1168641291 csharp
myCustomClose[0] = 25;

```

### Example \#2

## Note

Erroneous Sample Code - Cannot reassign values to Series< `double` \> indexed value and cannot have an if statement based on an assignment operator

```jsx-1168641291 csharp
if (Close[0] = Open[0])

```

## Note

Resolution Sample Code - Properly compares two Series< `double` \> values

```jsx-1168641291 csharp
if (Close[0] == Open[0])

```