## [Definition](https://developer.ninjatrader.com/docs/desktop/icon\#definition)

The shape which displays within the Share window when sharing content. Since this is a standard object, any type of icon can be used (unicode characters, custom image file resource, geometry path, etc). For more information on using images to create icons, see the [Using Images with Custom Icons](https://developer.ninjatrader.com/docs/desktop/using_images_and_geometry_with_custom_icons).

## Note

When using Unicode characters, first ensure that the desired characters exist in the icon pack for the font family used in NinjaTrader.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/icon\#property-value)

A generic virtual object representing the drawing tools menu icon. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/icon\#syntax)

You must override this property using the following syntax:

`public override object Icon`

## [Examples](https://developer.ninjatrader.com/docs/desktop/icon\#examples)

```jsx-150469391 csharp
public override object Icon
{
   get
   {
     //use a unicode character as our string which will render an arrow
     string uniCodeArrow = "\u279A";
     return uniCodeArrow;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/icon\#definition)

The shape which displays within the Share window when sharing content. Since this is a standard object, any type of icon can be used (unicode characters, custom image file resource, geometry path, etc). For more information on using images to create icons, see the [Using Images with Custom Icons](https://developer.ninjatrader.com/docs/desktop/using_images_and_geometry_with_custom_icons).

## Note

When using Unicode characters, first ensure that the desired characters exist in the icon pack for the font family used in NinjaTrader.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/icon\#property-value)

A generic virtual object representing the drawing tools menu icon. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/icon\#syntax)

You must override this property using the following syntax:

`public override object Icon`

## [Examples](https://developer.ninjatrader.com/docs/desktop/icon\#examples)

```jsx-150469391 csharp
public override object Icon
{
   get
   {
     //use a unicode character as our string which will render an arrow
     string uniCodeArrow = "\u279A";
     return uniCodeArrow;
   }
}

```