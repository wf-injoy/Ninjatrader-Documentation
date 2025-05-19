## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#description)

A Variable Moving Average is an exponential moving average that automatically adjusts its smoothing percentage based on market volatility. Giving more weight to the current data increases sensitivity thus making it a better signal indicator for short and long term markets.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#syntax)

`VMA(int period, int volatilityPeriod)`

`VMA(ISeries<double> input, int period, int volatilityPeriod)`

**Returns default value**

`VMA(int period, int volatilityPeriod)[int barsAgo]`

`VMA(ISeries<double> input, int period, int volatilityPeriod)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| volatilityPeriod | The number of bars used to calculate the [CMO](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo) based volatility index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a strategy
protected override void OnBarUpdate()
{
   // Print out the VMA value of lows 3 bars ago for fun
   double value = VMA(Low, 9, 9)[3];
   Print("The value is " + value.ToString());

   // Go long if price closes above the current VMA value
   if (Close[0] > VMA(9, 9)[0])
       EnterLong();
}

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#description)

A Variable Moving Average is an exponential moving average that automatically adjusts its smoothing percentage based on market volatility. Giving more weight to the current data increases sensitivity thus making it a better signal indicator for short and long term markets.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#syntax)

`VMA(int period, int volatilityPeriod)`

`VMA(ISeries<double> input, int period, int volatilityPeriod)`

**Returns default value**

`VMA(int period, int volatilityPeriod)[int barsAgo]`

`VMA(ISeries<double> input, int period, int volatilityPeriod)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#return-value)

**double;** Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#parameters)

| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | Number of bars used in the calculation |
| volatilityPeriod | The number of bars used to calculate the [CMO](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo) based volatility index |

## [Examples](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#examples)

```jsx-150469391 csharp
// OnBarUpdate method of a strategy
protected override void OnBarUpdate()
{
   // Print out the VMA value of lows 3 bars ago for fun
   double value = VMA(Low, 9, 9)[3];
   Print("The value is " + value.ToString());

   // Go long if price closes above the current VMA value
   if (Close[0] > VMA(9, 9)[0])
       EnterLong();
}

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/moving_average_variable_vma\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.