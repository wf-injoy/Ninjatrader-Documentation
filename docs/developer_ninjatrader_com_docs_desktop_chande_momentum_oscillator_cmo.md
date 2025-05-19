## [Description](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#description)

The Chande Momentum Oscillator was developed by Tushar S. Chande and is described in the 1994 book The New Technical Trader by Tushar S. Chande and Stanley Kroll. This indicator is a modified **RSI**. Where the **RSI** divides the upward movement by the net movement (up / (up + down)), the **CMO** divides the total movement by the net movement ((up - down) / (up + down)). Values under -50 indicate oversold conditions while values over 50 indicate overbought conditions.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#syntax)

`CMO(int period)`

`CMO(ISeries<double> input, int period)`

**Returns default value**

`CMO(int period)[int barsAgo]`

`CMO(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#parameters)

| input | Indicator source data ( [**Series< `T` >**](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | The number of bars to include in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period CMO using default price type
double value = CMO(20)[0];
Print("The current CMO value is " + value.ToString());

```

```jsx-150469391 csharp
// Prints the current value of a 20 period CMO using high price type
double value = CMO(High, 20)[0];
Print("The current CMO value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#description)

The Chande Momentum Oscillator was developed by Tushar S. Chande and is described in the 1994 book The New Technical Trader by Tushar S. Chande and Stanley Kroll. This indicator is a modified **RSI**. Where the **RSI** divides the upward movement by the net movement (up / (up + down)), the **CMO** divides the total movement by the net movement ((up - down) / (up + down)). Values under -50 indicate oversold conditions while values over 50 indicate overbought conditions.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#syntax)

`CMO(int period)`

`CMO(ISeries<double> input, int period)`

**Returns default value**

`CMO(int period)[int barsAgo]`

`CMO(ISeries<double> input, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#return-value)

**double;** Accessing this method via an index value \[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#parameters)

| input | Indicator source data ( [**Series< `T` >**](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| period | The number of bars to include in the calculation |

## [Examples](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#examples)

```jsx-150469391 csharp
// Prints the current value of a 20 period CMO using default price type
double value = CMO(20)[0];
Print("The current CMO value is " + value.ToString());

```

```jsx-150469391 csharp
// Prints the current value of a 20 period CMO using high price type
double value = CMO(High, 20)[0];
Print("The current CMO value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/chande_momentum_oscillator_cmo\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.