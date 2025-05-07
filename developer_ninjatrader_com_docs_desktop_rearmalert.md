## [Definition](https://developer.ninjatrader.com/docs/desktop/rearmalert\#definition)

Rearms an alert created via the **Alert()** method.

## Note

A NinjaScript generated alert may need to be rearmed after the alert is triggered depending on the **Alert()** method's **rearmSeconds** parameter.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/rearmalert\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rearmalert\#syntax)

`RearmAlert(string id)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rearmalert\#parameters)

| Parameter | Description |
| --- | --- |
| id | A unique string id representing an alert id to rearm |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rearmalert\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   //rearms "myAlert" on each new trading session
   if(Bars.IsFirstBarOfSession)
     RearmAlert("myAlert");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/rearmalert\#definition)

Rearms an alert created via the **Alert()** method.

## Note

A NinjaScript generated alert may need to be rearmed after the alert is triggered depending on the **Alert()** method's **rearmSeconds** parameter.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/rearmalert\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rearmalert\#syntax)

`RearmAlert(string id)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rearmalert\#parameters)

| Parameter | Description |
| --- | --- |
| id | A unique string id representing an alert id to rearm |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rearmalert\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
   //rearms "myAlert" on each new trading session
   if(Bars.IsFirstBarOfSession)
     RearmAlert("myAlert");
}

```