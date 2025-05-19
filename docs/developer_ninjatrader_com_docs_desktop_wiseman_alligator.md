## [Description](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#description)

The Wiseman Alligator is an indicator that consists of 3 moving averages with offsets applied to identify trend absence, formation, and direction. This indicator was provided by Profitunity: [http://www.profitunity.com](http://www.profitunity.com/)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#syntax)

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset)`

`Wiseman Alligator(ISeries<double> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset)`

**Returns Teeth**

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

**Returns Lips**

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Lips[int barsAgo]`

**Returns Jaw**

`**Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Jaw[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| jawPeriod | Number of bars used in the jaw moving average calculation |
| teethPeriod | Number of bars used in the teeth moving average calculation |
| lipsPeriod | Number of bars used in the lips moving average calculation |
| jawOffset | The offset for the jaw moving average |
| teethOffset | The offset for the teeth moving average |
| lipsOffset | The offset for the lips moving average |

## [Examples](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#examples)

```jsx-150469391 csharp
// Prints the current value of the teeth for the Wiseman Alligator
double value = WisemanAlligator(13, 8, 5, 8, 5, 3).Teeth[0];
Print("The current Wiseman Alligator teeth value is " + value.ToString());

```

## [Description](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#description)

The Wiseman Alligator is an indicator that consists of 3 moving averages with offsets applied to identify trend absence, formation, and direction. This indicator was provided by Profitunity: [http://www.profitunity.com](http://www.profitunity.com/)

## [Syntax](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#syntax)

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset)`

`Wiseman Alligator(ISeries<double> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset)`

**Returns Teeth**

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

**Returns Lips**

`Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Lips[int barsAgo]`

**Returns Jaw**

`**Wiseman Alligator(int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Teeth[int barsAgo]`

`Wiseman Alligator(ISeries<` double `> input, int jawPeriod, int teethPeriod, int lipsPeriod, int jawOffset, int teethOffset, int lipsOffset).Jaw[int barsAgo]`

## [Return Value](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#return-value)

**double**; Accessing this method via an index value `[int barsAgo]` returns the indicator value of the referenced bar

## [Parameters](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#parameters)

| Property | Description |
| --- | --- |
| input | Indicator source data ( [Series< `T` >](https://developer.ninjatrader.com/docs/desktop/seriest)) |
| jawPeriod | Number of bars used in the jaw moving average calculation |
| teethPeriod | Number of bars used in the teeth moving average calculation |
| lipsPeriod | Number of bars used in the lips moving average calculation |
| jawOffset | The offset for the jaw moving average |
| teethOffset | The offset for the teeth moving average |
| lipsOffset | The offset for the lips moving average |

## [Examples](https://developer.ninjatrader.com/docs/desktop/wiseman_alligator\#examples)

```jsx-150469391 csharp
// Prints the current value of the teeth for the Wiseman Alligator
double value = WisemanAlligator(13, 8, 5, 8, 5, 3).Teeth[0];
Print("The current Wiseman Alligator teeth value is " + value.ToString());

```