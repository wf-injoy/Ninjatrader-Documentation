## [Definition](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#definition)

Indicates the anchor's Y properties are visible on the UI. When set to true, the Y values can be viewed from the Drawing Objects properties.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#property-value)

A bool value which when true will display the anchor's Y (price) data values from the drawing object properties; otherwise false. Default value is true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#syntax)

`<chartanchor>.IsYPropertyVisibile`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          MyAnchor = new ChartAnchor();
          MyAnchor.IsYPropertyVisibile = true;
     }
     else if (State == State.Configure)
     {

     }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#definition)

Indicates the anchor's Y properties are visible on the UI. When set to true, the Y values can be viewed from the Drawing Objects properties.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#property-value)

A bool value which when true will display the anchor's Y (price) data values from the drawing object properties; otherwise false. Default value is true.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#syntax)

`<chartanchor>.IsYPropertyVisibile`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isypropertyvisibile\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
          MyAnchor = new ChartAnchor();
          MyAnchor.IsYPropertyVisibile = true;
     }
     else if (State == State.Configure)
     {

     }
}

```