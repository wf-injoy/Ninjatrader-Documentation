## [Definition](https://developer.ninjatrader.com/docs/desktop/onshare\#definition)

This method is called when the user clicks OK on the Share window in **NinjaTrader**. This method can also be called by Alerts and general **NinjaScript** objects.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onshare\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onshare\#parameters)

| **text** | The message being sent to the social network or other Share provider. This is what appears in the textbox of the Share window. |
| **imageFilePath** | Optional path to screenshot or other image to be sent to the social network or other Share provider. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onshare\#syntax)

You must override the method in your Share Service with the following syntax.

`public override void OnShare(string text, string imageFilePath)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/onshare\#examples)

```jsx-150469391 csharp
public override void OnShare(string text, string imgFilePath)
{
  // place your share service logic here
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onshare\#definition)

This method is called when the user clicks OK on the Share window in **NinjaTrader**. This method can also be called by Alerts and general **NinjaScript** objects.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onshare\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onshare\#parameters)

| **text** | The message being sent to the social network or other Share provider. This is what appears in the textbox of the Share window. |
| **imageFilePath** | Optional path to screenshot or other image to be sent to the social network or other Share provider. |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onshare\#syntax)

You must override the method in your Share Service with the following syntax.

`public override void OnShare(string text, string imageFilePath)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/onshare\#examples)

```jsx-150469391 csharp
public override void OnShare(string text, string imgFilePath)
{
  // place your share service logic here
}

```