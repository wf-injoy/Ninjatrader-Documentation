## [Definition](https://developer.ninjatrader.com/docs/desktop/displayname\#definition)

Sets the display name prefix used for all properties for a chart anchor.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displayname\#property-value)

A **string** value that is used to identify the name for a corresponding anchor. Default value is null.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displayname\#syntax)

`<chartanchor>.DisplayName`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displayname\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        MyAnchor = new ChartAnchor();
        MyAnchor.DisplayName = "MyChartAnchor";
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/displayname\#definition)

Sets the display name prefix used for all properties for a chart anchor.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/displayname\#property-value)

A **string** value that is used to identify the name for a corresponding anchor. Default value is null.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/displayname\#syntax)

`<chartanchor>.DisplayName`

## [Examples](https://developer.ninjatrader.com/docs/desktop/displayname\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        MyAnchor = new ChartAnchor();
        MyAnchor.DisplayName = "MyChartAnchor";
    }
}

```