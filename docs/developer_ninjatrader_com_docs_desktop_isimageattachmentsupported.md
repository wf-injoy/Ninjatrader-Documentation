## [Definition](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#definition)

Determines if the Share Service will allow for images as attachments.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#property-value)

A bool value when false, screenshots will be unable to be sent to the social network.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#syntax)

`IsImageAttachmentSupported`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      IsImageAttachmentSupported = false;
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#definition)

Determines if the Share Service will allow for images as attachments.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#property-value)

A bool value when false, screenshots will be unable to be sent to the social network.

## Warning

This property should ONLY be set from the **OnStateChange()** method during **State.SetDefaults** or **State.Configure**.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#syntax)

`IsImageAttachmentSupported`

## [Examples](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
   if (State == State.SetDefaults)
   {
      IsImageAttachmentSupported = false;
   }
}

```