## [Definition](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#definition)

Informs the Strategy Analyzer how many iterations of optimizing it needs to do.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#property-value)

An **int** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#syntax)

`NumberOfIterations`

## [Examples](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
         Name = "MyOptimizer";
     else if (State == State.Configure && Strategies.Count > 0)
         NumberOfIterations = 1;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#definition)

Informs the Strategy Analyzer how many iterations of optimizing it needs to do.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#property-value)

An **int** value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#syntax)

`NumberOfIterations`

## [Examples](https://developer.ninjatrader.com/docs/desktop/numberofiterations\#examples)

```jsx-150469391 csharp
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
         Name = "MyOptimizer";
     else if (State == State.Configure && Strategies.Count > 0)
         NumberOfIterations = 1;
}

```