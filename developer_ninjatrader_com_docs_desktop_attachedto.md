## [Definition](https://developer.ninjatrader.com/docs/desktop/attachedto\#definition)

An object which holds information regarding where the drawing tool is attached.

## [Available Properties](https://developer.ninjatrader.com/docs/desktop/attachedto\#available-properties)

| Name | Description |
| --- | --- |
| AttachedToType | An enum representing the type of object the drawing tool is attached. Possible values are:<br>- Bars - The chart bars of the parent chart<br>  <br>- GlobalInstrument - The bars of an instrument across all charts<br>  <br>- Indicator - A NinjaScript indicator<br>  <br>- Strategy - A NinjaScript strategy |
| ChartObject | A ChartObject interface such as an indicator, strategy, chart bars |
| DisplayName | A **string** value indicating the name of the object the drawing tool is attached |
| Instrument | The Instrument that the drawing tool is attached |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/attachedto\#syntax)

`AttachedTo`

## [Examples](https://developer.ninjatrader.com/docs/desktop/attachedto\#examples)

```jsx-150469391 csharp

if (AttachedTo.AttachedToType == AttachedToType.Indicator)
   // do something

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/attachedto\#definition)

An object which holds information regarding where the drawing tool is attached.

## [Available Properties](https://developer.ninjatrader.com/docs/desktop/attachedto\#available-properties)

| Name | Description |
| --- | --- |
| AttachedToType | An enum representing the type of object the drawing tool is attached. Possible values are:<br>- Bars - The chart bars of the parent chart<br>  <br>- GlobalInstrument - The bars of an instrument across all charts<br>  <br>- Indicator - A NinjaScript indicator<br>  <br>- Strategy - A NinjaScript strategy |
| ChartObject | A ChartObject interface such as an indicator, strategy, chart bars |
| DisplayName | A **string** value indicating the name of the object the drawing tool is attached |
| Instrument | The Instrument that the drawing tool is attached |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/attachedto\#syntax)

`AttachedTo`

## [Examples](https://developer.ninjatrader.com/docs/desktop/attachedto\#examples)

```jsx-150469391 csharp

if (AttachedTo.AttachedToType == AttachedToType.Indicator)
   // do something

```