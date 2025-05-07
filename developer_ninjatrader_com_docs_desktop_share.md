## [Definition](https://developer.ninjatrader.com/docs/desktop/share\#definition)

Sends a message or screen shot to a social network or Share Service.

## Note

1. This method can only be called once the **State** has reached **State.Realtime**. Calls to this method in any other State will be silently ignored.
2. You MUST configure an account with a Share Service provider from the **General Options**.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/share\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/share\#syntax)

`Share(string serviceName, string message)`

`Share(string serviceName, string message, object[] args)`

`Share(string serviceName, string message, string screenshotPath)`

`Share(string serviceName, string message, string screenshotPath, object[] args)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/share\#parameters)

| Parameter | Description |
| --- | --- |
| **serviceName** | A **string** value representing the share service to be used |
| **message** | A **string** value representing the text body sent to the social network or other Share providers. Note: The message is what appears in the text box of the Share window |
| **screenshotPath** | Optional string path to screenshot or other images sent to the social network or other Share providers |
| **args** | A generic object\[\] array used to designate additional information sent to the share service |

## Note

1. The "args" parameter differs for each share service used. If you are using a custom developed share adapter, you need to work with the developer of that adapter to understand what the "args" parameter represents for that adapter.
2. For the default NinjaTrader share adapters, the "args" array represents the following:
   - Mail share service:
     - args\[0\] = A string representing the email "To" field,
     - args\[1\] = A string representing the email "Subject" field
   - StockTwits share service:
     - args\[0\] = An enum representing the "StockTwitsSentiment" parameter

## [Examples](https://developer.ninjatrader.com/docs/desktop/share\#examples)

```jsx-150469391 csharp
// using "args" as the Mail "To" and "Subject" parameters
Share("Gmail", "Test Message", new object[]{ "example@test.com", "Test Subject Line" });

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/share\#definition)

Sends a message or screen shot to a social network or Share Service.

## Note

1. This method can only be called once the **State** has reached **State.Realtime**. Calls to this method in any other State will be silently ignored.
2. You MUST configure an account with a Share Service provider from the **General Options**.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/share\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/share\#syntax)

`Share(string serviceName, string message)`

`Share(string serviceName, string message, object[] args)`

`Share(string serviceName, string message, string screenshotPath)`

`Share(string serviceName, string message, string screenshotPath, object[] args)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/share\#parameters)

| Parameter | Description |
| --- | --- |
| **serviceName** | A **string** value representing the share service to be used |
| **message** | A **string** value representing the text body sent to the social network or other Share providers. Note: The message is what appears in the text box of the Share window |
| **screenshotPath** | Optional string path to screenshot or other images sent to the social network or other Share providers |
| **args** | A generic object\[\] array used to designate additional information sent to the share service |

## Note

1. The "args" parameter differs for each share service used. If you are using a custom developed share adapter, you need to work with the developer of that adapter to understand what the "args" parameter represents for that adapter.
2. For the default NinjaTrader share adapters, the "args" array represents the following:
   - Mail share service:
     - args\[0\] = A string representing the email "To" field,
     - args\[1\] = A string representing the email "Subject" field
   - StockTwits share service:
     - args\[0\] = An enum representing the "StockTwitsSentiment" parameter

## [Examples](https://developer.ninjatrader.com/docs/desktop/share\#examples)

```jsx-150469391 csharp
// using "args" as the Mail "To" and "Subject" parameters
Share("Gmail", "Test Message", new object[]{ "example@test.com", "Test Subject Line" });

```