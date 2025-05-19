## [Description](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#description)

The ADXR is equal to the current [ADX](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx) plus the ADX from n bars ago divided by two.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#syntax)

`ADXR(int interval, int period)`

`ADXR(ISeries<double> input, int interval, int period)`

**Returns default value**

`ADXR(int interval, int period)[int barsAgo]`

`ADXR(ISeries<double> input, int interval, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#return-value)

**double**; Accessing this method via an index value \`\[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#parameters)

| input | Indicator source data |
| --- | --- |
| interval | The interval between the first ADX value and the current ADX value |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#example)

```jsx-150469391 csharp
// Prints the current value of a 20 period ADXR using default price type
double value = ADXR(10, 20)[0];
Print("The current ADXR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.

## [Description](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#description)

The ADXR is equal to the current [ADX](https://developer.ninjatrader.com/docs/desktop/average_directional_index_adx) plus the ADX from n bars ago divided by two.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#syntax)

`ADXR(int interval, int period)`

`ADXR(ISeries<double> input, int interval, int period)`

**Returns default value**

`ADXR(int interval, int period)[int barsAgo]`

`ADXR(ISeries<double> input, int interval, int period)[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#return-value)

**double**; Accessing this method via an index value \`\[int barsAgo\] returns the indicator value of the referenced bar.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#parameters)

| input | Indicator source data |
| --- | --- |
| interval | The interval between the first ADX value and the current ADX value |
| period | Number of bars used in the calculation |

## [Example](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#example)

```jsx-150469391 csharp
// Prints the current value of a 20 period ADXR using default price type
double value = ADXR(10, 20)[0];
Print("The current ADXR value is " + value.ToString());

```

## [Source Code](https://developer.ninjatrader.com/docs/desktop/average_directional_movement_rating_adxr\#source-code)

You can view this indicator method source code by selecting the menu New > NinjaScript Editor > Indicators within the NinjaTrader Control Center window.