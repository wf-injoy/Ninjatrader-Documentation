## [Definition](https://developer.ninjatrader.com/docs/desktop/flatten\#definition)

Flattens the account on an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/flatten\#syntax)

`Flatten(ICollection<instrument> instruments)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/flatten\#parameters)

| instruments | A collection of Instruments for orders to be cancelled and positions closed |

## [Examples](https://developer.ninjatrader.com/docs/desktop/flatten\#examples)

### Flatten a single instrument

```jsx-1168641291 csharp
Account.Flatten(new [] { Instrument.GetInstrument("ES 12-15") });

```

### Flatten a list of instruments

```jsx-150469391 csharp
// Please note that your 'Using declarations' section needs to have
//
// using System.Collections.ObjectModel;
//
//added in order for this example to compile correctly

// instantiate a list of instruments
Collection<cbi.instrument> instrumentsToClose = new Collection<instrument>();

// add instruments to the collection
instrumentsToClose.Add(Instrument.GetInstrument("AAPL"));
instrumentsToClose.Add(Instrument.GetInstrument("MSFT"));

// pass the instrument collection to the Flatten() method to be flattened
Account.Flatten(instrumentsToClose);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/flatten\#definition)

Flattens the account on an instrument.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/flatten\#syntax)

`Flatten(ICollection<instrument> instruments)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/flatten\#parameters)

| instruments | A collection of Instruments for orders to be cancelled and positions closed |

## [Examples](https://developer.ninjatrader.com/docs/desktop/flatten\#examples)

### Flatten a single instrument

```jsx-1168641291 csharp
Account.Flatten(new [] { Instrument.GetInstrument("ES 12-15") });

```

### Flatten a list of instruments

```jsx-150469391 csharp
// Please note that your 'Using declarations' section needs to have
//
// using System.Collections.ObjectModel;
//
//added in order for this example to compile correctly

// instantiate a list of instruments
Collection<cbi.instrument> instrumentsToClose = new Collection<instrument>();

// add instruments to the collection
instrumentsToClose.Add(Instrument.GetInstrument("AAPL"));
instrumentsToClose.Add(Instrument.GetInstrument("MSFT"));

// pass the instrument collection to the Flatten() method to be flattened
Account.Flatten(instrumentsToClose);

```