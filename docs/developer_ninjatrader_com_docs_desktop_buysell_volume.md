## [Description](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#description)

The **BuySellVolume** indicator displays a real-time horizontal histogram of volume categorized as buy or sell trades. Trades are categorized in real-time as a buy (at the ask or above) or as a sell (at the bid or below) and then color coded. Trades in between the market are ignored.

## Note

For historical calculations, [Tick Replay](https://ninjatrader.com/support/helpGuides/nt8/?tick_replay.htm) must be enabled.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#syntax)

`BuySellVolume()`

`BuySellVolume(ISeries<double> input)`

**Returns buy volume**

`BuySellVolume().Buys[int barsAgo]`

`BuySellVolume(ISeries<double> input).Buys[int barsAgo]`

**Returns sell volume**

`BuySellVolume().Sells[int barsAgo]`

`BuySellVolume(ISeries<double> input).Sells[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#parameters)

| **Parameter** | **Description** |
| --- | --- |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Indicators will inherit the Calculate mode from the hosting script.
        // Since BuySellVolume requires the use of Calculate.OnEachTick, we must ensure the hosting script has this Calculate mode set
        Calculate = Calculate.OnEachTick;
    }
}

protected override void OnBarUpdate()
{
    // This checks that 5,000 or more of the volume hit the bid or lower
    if (State == State.Historical || BuySellVolume().Sells[0] > 5000)
    {
        EnterLong();
    }
}

```

## Note

Tip: Since this indicator operates in a real-time environment, remember to check for **State.Realtime**, or enable **Tick Replay** on the associated Data Series. In the above example we check that 5,000 or more of the volume hit the bid or lower. Our statement checks if the data is being calculated on historical data first; if true, we enter long. If not true (live), the statement then checks for the Buy Volume condition.

## [Source Code](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#description)

The **BuySellVolume** indicator displays a real-time horizontal histogram of volume categorized as buy or sell trades. Trades are categorized in real-time as a buy (at the ask or above) or as a sell (at the bid or below) and then color coded. Trades in between the market are ignored.

## Note

For historical calculations, [Tick Replay](https://ninjatrader.com/support/helpGuides/nt8/?tick_replay.htm) must be enabled.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#syntax)

`BuySellVolume()`

`BuySellVolume(ISeries<double> input)`

**Returns buy volume**

`BuySellVolume().Buys[int barsAgo]`

`BuySellVolume(ISeries<double> input).Buys[int barsAgo]`

**Returns sell volume**

`BuySellVolume().Sells[int barsAgo]`

`BuySellVolume(ISeries<double> input).Sells[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#return-value)

**double;** Accessing this method via an index value **\[int barsAgo\]** returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#parameters)

| **Parameter** | **Description** |
| --- | --- |
| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |

## [Examples](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
    if (State == State.SetDefaults)
    {
        // Indicators will inherit the Calculate mode from the hosting script.
        // Since BuySellVolume requires the use of Calculate.OnEachTick, we must ensure the hosting script has this Calculate mode set
        Calculate = Calculate.OnEachTick;
    }
}

protected override void OnBarUpdate()
{
    // This checks that 5,000 or more of the volume hit the bid or lower
    if (State == State.Historical || BuySellVolume().Sells[0] > 5000)
    {
        EnterLong();
    }
}

```

## Note

Tip: Since this indicator operates in a real-time environment, remember to check for **State.Realtime**, or enable **Tick Replay** on the associated Data Series. In the above example we check that 5,000 or more of the volume hit the bid or lower. Our statement checks if the data is being calculated on historical data first; if true, we enter long. If not true (live), the statement then checks for the Buy Volume condition.

## [Source Code](https://developer.ninjatrader.com/docs/desktop/buysell_volume\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.