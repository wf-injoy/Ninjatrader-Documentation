## [Definition](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#definition)

The optimization parameters selected for the optimization run. (e.g. user parameters or Data Series)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#property-value)

A bool value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#syntax)

`Strategies[0].OptimizationParameters`

## [Examples](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#examples)

```jsx-150469391 csharp
protected override void OnOptimize()
{
     // If there are no optimization parameters to optimize, return
     if (Strategies[0].OptimizationParameters.Count == 0)
         return;

     // Do something with the optimization parameter
     Parameter parameter = Strategies[0].OptimizationParameters[0];
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#definition)

The optimization parameters selected for the optimization run. (e.g. user parameters or Data Series)

## [Property Value](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#property-value)

A bool value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#syntax)

`Strategies[0].OptimizationParameters`

## [Examples](https://developer.ninjatrader.com/docs/desktop/optimizationparameters\#examples)

```jsx-150469391 csharp
protected override void OnOptimize()
{
     // If there are no optimization parameters to optimize, return
     if (Strategies[0].OptimizationParameters.Count == 0)
         return;

     // Do something with the optimization parameter
     Parameter parameter = Strategies[0].OptimizationParameters[0];
}

```