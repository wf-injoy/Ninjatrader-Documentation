## [Definition](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#definition)

Determines if the anchor are visible on the UI. When set to true, the anchors Y and X values can be viewed from the Drawing Objects properties.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#property-value)

A bool value which when true will display the anchor data values from the drawing object properties; otherwise false. Default value is true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#syntax)

`<chartanchor>.IsBrowsable`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          MyAnchor = new ChartAnchor();
          MyAnchor.IsBrowsable = true;
     }
     else if (State == State.Configure)
     {
     }
}
```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#definition)

Determines if the anchor are visible on the UI. When set to true, the anchors Y and X values can be viewed from the Drawing Objects properties.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#property-value)

A bool value which when true will display the anchor data values from the drawing object properties; otherwise false. Default value is true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#syntax)

`<chartanchor>.IsBrowsable`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isbrowsable\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          MyAnchor = new ChartAnchor();
          MyAnchor.IsBrowsable = true;
     }
     else if (State == State.Configure)
     {
     }
}
```