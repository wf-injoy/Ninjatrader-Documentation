## [Description](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#description)

Evaluates for n number of consecutive higher closes. Returns a value of 1 when the condition is true or 0 when false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#syntax)

`NBarsUp(int barCount, bool barUp, bool higherHigh, bool higherLow)`

`NBarsUp(ISeries<double> input, int barCount, bool barUp, bool higherHigh, bool higherLow)`

**Returns default value**

`NBarsUp(int barCount, bool barUp, bool higherHigh, bool higherLow)[int barsAgo]`

`NBarsUp(ISeries<double> input, int barCount, bool barUp, bool higherHigh, bool higherLow)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **barCount** | The number of required consecutive higher closes |
| **barUp** | Each bar's close must be higher than the open; true or false |
| **higherHigh** | Consecutive higher highs required; true or false |
| **higherLow** | Consecutive higher lows required; true or false |

## [Examples](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#examples)

```jsx-150469391 csharp
// OnBarUpdate method
protected override void OnBarUpdate()
{
   // Evaluates if we have 3 consecutive higher closes
   double value = NBarsUp(3, true, true, true)[0];

   if (value == 1)
       Print("We have three consecutive higher closes");
}

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#description)

Evaluates for n number of consecutive higher closes. Returns a value of 1 when the condition is true or 0 when false.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#syntax)

`NBarsUp(int barCount, bool barUp, bool higherHigh, bool higherLow)`

`NBarsUp(ISeries<double> input, int barCount, bool barUp, bool higherHigh, bool higherLow)`

**Returns default value**

`NBarsUp(int barCount, bool barUp, bool higherHigh, bool higherLow)[int barsAgo]`

`NBarsUp(ISeries<double> input, int barCount, bool barUp, bool higherHigh, bool higherLow)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#parameters)

| **input** | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| **barCount** | The number of required consecutive higher closes |
| **barUp** | Each bar's close must be higher than the open; true or false |
| **higherHigh** | Consecutive higher highs required; true or false |
| **higherLow** | Consecutive higher lows required; true or false |

## [Examples](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#examples)

```jsx-150469391 csharp
// OnBarUpdate method
protected override void OnBarUpdate()
{
   // Evaluates if we have 3 consecutive higher closes
   double value = NBarsUp(3, true, true, true)[0];

   if (value == 1)
       Print("We have three consecutive higher closes");
}

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/n_bars_up\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.