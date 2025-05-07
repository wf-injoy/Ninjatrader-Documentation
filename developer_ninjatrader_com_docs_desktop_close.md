## [Definition](https://developer.ninjatrader.com/docs/desktop/close\#definition)

A collection of historical bar close prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/close\#property-value)

A **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## Note

When an indicator uses another indicator as input series, Close will represent the closing price of the input series' input series. For example, if MyCustomIndicator uses an ADX as input series, then referencing **Close\[0\]** in MyCustomIndicator will provide the Close price for the ADX's input series.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/close\#syntax)

`Close`

`Close[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/close\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Evaluates if the current close is greater than the prior bar close
     if (Close[0] > Close[1])
         Print("We had an up day");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/close\#definition)

A collection of historical bar close prices.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/close\#property-value)

A **ISeries `<double>`** type object. Accessing this property via an index value **int barsAgo** returns A **double** value representing the price of the referenced bar.

## Note

When an indicator uses another indicator as input series, Close will represent the closing price of the input series' input series. For example, if MyCustomIndicator uses an ADX as input series, then referencing **Close\[0\]** in MyCustomIndicator will provide the Close price for the ADX's input series.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/close\#syntax)

`Close`

`Close[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/close\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
     // Evaluates if the current close is greater than the prior bar close
     if (Close[0] > Close[1])
         Print("We had an up day");
}

```