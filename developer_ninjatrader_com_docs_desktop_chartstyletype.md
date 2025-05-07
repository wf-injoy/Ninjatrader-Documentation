## [Definition](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#definition)

Defines a unique identifier value used to register a custom **ChartStyle**. There are 11 default **ChartStyles** which come with **NinjaTrader** which are reserved per the table on this page under the Parameters section of this page.

## Note

The **ChartStyle** property can allow a large number of **ChartStyles** to be registered on a single user's installation (up to 2,147,483,647). However, it's important to note that it is still possible for two installed **ChartStyles** on a user's computer to conflict should they be registered to the same enumerator value. In this case, **NinjaTrader** will ignore the conflicting **ChartStyle** type and information pertaining to this conflict will be displayed on the [Log tab](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?log_tab2.htm).

**Added 1/31/2018**: We advise users to use values larger than 1023 when selecting an enum. As **NinjaTrader** from time to time may add a new enum value in that range which may cause conflicts.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#property-value)

A enum value representing the **ChartStyle** to be registered.

## Note

It is recommended to pick high, unique enumeration value to avoid conflict from other **ChartStyles** that may be used by a single installation.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#syntax)

You must cast `ChartStyleType` from an `int` using the following syntax:

`ChartStyleType = (ChartStyleType) 80;`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#parameters)

Reserved enumeration values are listed below:

| Value | ChartStyle |
| --- | --- |
| 0 | Box |
| 1 | CandleStick |
| 2 | LineOnClose |
| 3 | OHLC |
| 4 | PointAndFigure |
| 5 | KagiLine |
| 6 | OpenClose |
| 7 | Mountain |
| 8 | Volumetric |
| 9 | HollowCandleStick |
| 10 | Equivolume |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name            = "Example ChartStyle";
        ChartStyleType = (ChartStyleType) 80;
        BarWidth       = 1;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#definition)

Defines a unique identifier value used to register a custom **ChartStyle**. There are 11 default **ChartStyles** which come with **NinjaTrader** which are reserved per the table on this page under the Parameters section of this page.

## Note

The **ChartStyle** property can allow a large number of **ChartStyles** to be registered on a single user's installation (up to 2,147,483,647). However, it's important to note that it is still possible for two installed **ChartStyles** on a user's computer to conflict should they be registered to the same enumerator value. In this case, **NinjaTrader** will ignore the conflicting **ChartStyle** type and information pertaining to this conflict will be displayed on the [Log tab](https://ninjatrader.com/support/helpGuides/nt8/NT%20HelpGuide%20English.html?log_tab2.htm).

**Added 1/31/2018**: We advise users to use values larger than 1023 when selecting an enum. As **NinjaTrader** from time to time may add a new enum value in that range which may cause conflicts.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#property-value)

A enum value representing the **ChartStyle** to be registered.

## Note

It is recommended to pick high, unique enumeration value to avoid conflict from other **ChartStyles** that may be used by a single installation.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#syntax)

You must cast `ChartStyleType` from an `int` using the following syntax:

`ChartStyleType = (ChartStyleType) 80;`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#parameters)

Reserved enumeration values are listed below:

| Value | ChartStyle |
| --- | --- |
| 0 | Box |
| 1 | CandleStick |
| 2 | LineOnClose |
| 3 | OHLC |
| 4 | PointAndFigure |
| 5 | KagiLine |
| 6 | OpenClose |
| 7 | Mountain |
| 8 | Volumetric |
| 9 | HollowCandleStick |
| 10 | Equivolume |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chartstyletype\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        Name            = "Example ChartStyle";
        ChartStyleType = (ChartStyleType) 80;
        BarWidth       = 1;
    }
}

```