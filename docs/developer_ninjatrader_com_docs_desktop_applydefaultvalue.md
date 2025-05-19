## [Definition](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#definition)

Sets the default **BarsPeriod** values used for a custom Bar Type.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#parameters)

| period | The [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) chosen by the user when utilizing this Bars type |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#syntax)

You must override the method in your Bars Type with the following syntax:

`public override void ApplyDefaultValue(BarsPeriod period)  {  }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#examples)

```jsx-150469391 csharp
public override void ApplyDefaultValue(BarsPeriod period)
{
		period.BarsPeriodTypeName = "MyBarType";
		period.Value = 1;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#definition)

Sets the default **BarsPeriod** values used for a custom Bar Type.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#method-return-value)

This method does not return a value.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#parameters)

| period | The [BarsPeriod](https://developer.ninjatrader.com/docs/desktop/barsperiod) chosen by the user when utilizing this Bars type |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#syntax)

You must override the method in your Bars Type with the following syntax:

`public override void ApplyDefaultValue(BarsPeriod period)  {  }`

## [Examples](https://developer.ninjatrader.com/docs/desktop/applydefaultvalue\#examples)

```jsx-150469391 csharp
public override void ApplyDefaultValue(BarsPeriod period)
{
		period.BarsPeriodTypeName = "MyBarType";
		period.Value = 1;
}

```