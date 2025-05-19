Custom Share Services can be developed in order to enable users to share content from the NinjaTrader application to various websites and social media networks via the **Sharing Services** dialog. NinjaTrader comes pre-configured with Share Services for an Email adapter and Test message via email adapter, however a custom adapter can be developed for any website, forum, or social media network by following their public API documentation and guidelines.

## [In this section](https://developer.ninjatrader.com/docs/desktop/share_service\#in-this-section)

| [CharacterLimit](https://developer.ninjatrader.com/docs/desktop/characterlimit) | Determines the maximum number of characters the social network allows. |
| [CharactersReservedPerMedia](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia) | Sets the number of characters allowed when attaching an image to ensure that character count is properly calculated. |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon) | The shape which displays within the Share window when sharing content. |
| [UseOAuth](https://developer.ninjatrader.com/docs/desktop/useoauth) | If this property is set to true, a Connect button will appear in the dialogue for configuring the adapter that will call **OnAuthorizeAccount()** when the user clicks it. |
| [IsConfigured](https://developer.ninjatrader.com/docs/desktop/isconfigured) | Sets when the Share Service is correctly configured. |
| [IsDefault](https://developer.ninjatrader.com/docs/desktop/isdefault) | Sets the default Share Service used when the type of sharing service is selected (email for example). |
| [IsImageAttachmentSupported](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported) | Determines if the Share Service will allow for images as attachments. |
| [OnAuthorizeAccount](https://developer.ninjatrader.com/docs/desktop/onauthorizeaccount) | If the **UseOAuth** property is set to true, this method will be called when the user clicks the Connect button in the Share Services dialogue under Tools -> **Options**. |
| [OnShare](https://developer.ninjatrader.com/docs/desktop/onshare) | This method is called when the user clicks OK on the Share window in NinjaTrader. This method can also be called by Alerts and general NinjaScript objects. |
| [Signature](https://developer.ninjatrader.com/docs/desktop/signature) | Sets the text appended to the end of the user's message. |

Custom Share Services can be developed in order to enable users to share content from the NinjaTrader application to various websites and social media networks via the **Sharing Services** dialog. NinjaTrader comes pre-configured with Share Services for an Email adapter and Test message via email adapter, however a custom adapter can be developed for any website, forum, or social media network by following their public API documentation and guidelines.

## [In this section](https://developer.ninjatrader.com/docs/desktop/share_service\#in-this-section)

| [CharacterLimit](https://developer.ninjatrader.com/docs/desktop/characterlimit) | Determines the maximum number of characters the social network allows. |
| [CharactersReservedPerMedia](https://developer.ninjatrader.com/docs/desktop/charactersreservedpermedia) | Sets the number of characters allowed when attaching an image to ensure that character count is properly calculated. |
| [Icon](https://developer.ninjatrader.com/docs/desktop/icon) | The shape which displays within the Share window when sharing content. |
| [UseOAuth](https://developer.ninjatrader.com/docs/desktop/useoauth) | If this property is set to true, a Connect button will appear in the dialogue for configuring the adapter that will call **OnAuthorizeAccount()** when the user clicks it. |
| [IsConfigured](https://developer.ninjatrader.com/docs/desktop/isconfigured) | Sets when the Share Service is correctly configured. |
| [IsDefault](https://developer.ninjatrader.com/docs/desktop/isdefault) | Sets the default Share Service used when the type of sharing service is selected (email for example). |
| [IsImageAttachmentSupported](https://developer.ninjatrader.com/docs/desktop/isimageattachmentsupported) | Determines if the Share Service will allow for images as attachments. |
| [OnAuthorizeAccount](https://developer.ninjatrader.com/docs/desktop/onauthorizeaccount) | If the **UseOAuth** property is set to true, this method will be called when the user clicks the Connect button in the Share Services dialogue under Tools -> **Options**. |
| [OnShare](https://developer.ninjatrader.com/docs/desktop/onshare) | This method is called when the user clicks OK on the Share window in NinjaTrader. This method can also be called by Alerts and general NinjaScript objects. |
| [Signature](https://developer.ninjatrader.com/docs/desktop/signature) | Sets the text appended to the end of the user's message. |