## [Definition](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#definition)

Determines if the bars type can use the **RemoveLastBar()** method when true, otherwise an exception will be thrown. Bar Types which use remove last bar concepts CANNOT be used with **Tick Replay**, and as a result Tick Replay will be disabled on the UI when **IsRemoveLastBarSupported** is set to true.

## Note

This property is read-only, but may be overridden in a custom bar type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#syntax)

`IsRemoveLastBarSupported`

## [Property value](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#property-value)

A **bool** determining if the BarsType can remove the last; default value is false.

## [Examples](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#examples)

```jsx-150469391 csharp
// allows RemoveLastBar() to be called
public override bool IsRemoveLastBarSupported { get { return true; } }

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#definition)

Determines if the bars type can use the **RemoveLastBar()** method when true, otherwise an exception will be thrown. Bar Types which use remove last bar concepts CANNOT be used with **Tick Replay**, and as a result Tick Replay will be disabled on the UI when **IsRemoveLastBarSupported** is set to true.

## Note

This property is read-only, but may be overridden in a custom bar type.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#syntax)

`IsRemoveLastBarSupported`

## [Property value](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#property-value)

A **bool** determining if the BarsType can remove the last; default value is false.

## [Examples](https://developer.ninjatrader.com/docs/desktop/isremovelastbarsupported\#examples)

```jsx-150469391 csharp
// allows RemoveLastBar() to be called
public override bool IsRemoveLastBarSupported { get { return true; } }

```