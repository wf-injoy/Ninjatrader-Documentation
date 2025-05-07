## [Definition](https://developer.ninjatrader.com/docs/desktop/time\#definition)

A collection of historical bar time stamp values.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/time\#property-value)

An **ISeries< `datetime` >** object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/time\#syntax)

`Time`

**Returns a DateTime structure**

`Time[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/time\#examples)

```jsx-150469391 csharp
// Prints the current bar time stamp
Print(Time[0].ToString());

//Checks if current time is greater than the bar time stamp
if (DateTime.Now.Ticks > Time[0].Ticks)
 Print("Do something");

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/time\#definition)

A collection of historical bar time stamp values.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/time\#property-value)

An **ISeries< `datetime` >** object.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/time\#syntax)

`Time`

**Returns a DateTime structure**

`Time[int barsAgo]`

## [Examples](https://developer.ninjatrader.com/docs/desktop/time\#examples)

```jsx-150469391 csharp
// Prints the current bar time stamp
Print(Time[0].ToString());

//Checks if current time is greater than the bar time stamp
if (DateTime.Now.Ticks > Time[0].Ticks)
 Print("Do something");

```