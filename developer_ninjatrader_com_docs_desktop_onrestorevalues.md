## [Definition](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#definition)

Called when the column is restored (e.g. from a workspace). All public properties in a SuperDOM Column are saved to the workspace upon closing and selecting save. You may choose to do something explicit with a certain property when the **OnRestoreValues()** method is called.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#syntax)

You may override the method in your SuperDOM column with the following syntax:

`public override void OnRestoreValues()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#parameters)

This method does not require any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#examples)

```jsx-150469391 csharp
public override void OnRestoreValues()
{
   // Do something with the restored values. Can also trigger a repaint via OnPropertyChanged()
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#definition)

Called when the column is restored (e.g. from a workspace). All public properties in a SuperDOM Column are saved to the workspace upon closing and selecting save. You may choose to do something explicit with a certain property when the **OnRestoreValues()** method is called.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#syntax)

You may override the method in your SuperDOM column with the following syntax:

`public override void OnRestoreValues()`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#parameters)

This method does not require any parameters.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onrestorevalues\#examples)

```jsx-150469391 csharp
public override void OnRestoreValues()
{
   // Do something with the restored values. Can also trigger a repaint via OnPropertyChanged()
}

```