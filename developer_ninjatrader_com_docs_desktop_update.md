## [Definition](https://developer.ninjatrader.com/docs/desktop/update\#definition)

Forces the OnBarUpdate() method to be called for all data series so that indicator values are updated to the current bar index.  If the values are already up to date, the Update() method will not be run.

## Note

- This method is only relevant in specific use cases and should only used by advanced programmers

- The additional overload where a bar index and [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) are specified should only be used when an indicator needs to be updated to a bar index that is not the [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) index. For example, updating an indicator's secondary 1 tick data series to indicator.BarsArray\[1\].Count - 1, which is not the [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) index. This is required for the proper function of [Order Flow Cumulative Delta](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta) and [Order Flow VWAP](https://developer.ninjatrader.com/docs/desktop/order_flow_vwap)


When indicators are embedded (called) within a NinjaScript strategy, they are optimized to calculate only when they are called upon in a historical backtest. Since the NinjaTrader indicator model is very flexible, it is possible to create public properties on a custom indicator that return values of internal user defined variables. If these properties require that the OnBarUpdate() method is called before returning a value, include a call to this Update() method in the property getter.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/update\#syntax)

`Update()`

`Update(int idx, int bip)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/update\#parameters)

| Parameter | Description |
| --- | --- |
| idx | The current bar index value to update to |
| bip | The [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) to update |

## [Examples](https://developer.ninjatrader.com/docs/desktop/update\#examples)

```jsx-150469391 csharp
private double tripleValue = 0;

protected override void OnBarUpdate()
{
  if (CurrentBar < 20)
      return;

  tripleValue = SMA(20)[0] * 3;
  Value[0] = SMA(20)[0];
}

public double TripleValue
{
    get
    {
      //call OnBarUpdate before returning tripleValue
      Update();
      return tripleValue;
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/update\#definition)

Forces the OnBarUpdate() method to be called for all data series so that indicator values are updated to the current bar index.  If the values are already up to date, the Update() method will not be run.

## Note

- This method is only relevant in specific use cases and should only used by advanced programmers

- The additional overload where a bar index and [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) are specified should only be used when an indicator needs to be updated to a bar index that is not the [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) index. For example, updating an indicator's secondary 1 tick data series to indicator.BarsArray\[1\].Count - 1, which is not the [CurrentBar](https://developer.ninjatrader.com/docs/desktop/currentbar) index. This is required for the proper function of [Order Flow Cumulative Delta](https://developer.ninjatrader.com/docs/desktop/order_flow_cumulative_delta) and [Order Flow VWAP](https://developer.ninjatrader.com/docs/desktop/order_flow_vwap)


When indicators are embedded (called) within a NinjaScript strategy, they are optimized to calculate only when they are called upon in a historical backtest. Since the NinjaTrader indicator model is very flexible, it is possible to create public properties on a custom indicator that return values of internal user defined variables. If these properties require that the OnBarUpdate() method is called before returning a value, include a call to this Update() method in the property getter.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/update\#syntax)

`Update()`

`Update(int idx, int bip)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/update\#parameters)

| Parameter | Description |
| --- | --- |
| idx | The current bar index value to update to |
| bip | The [BarsInProgress](https://developer.ninjatrader.com/docs/desktop/barsinprogress) to update |

## [Examples](https://developer.ninjatrader.com/docs/desktop/update\#examples)

```jsx-150469391 csharp
private double tripleValue = 0;

protected override void OnBarUpdate()
{
  if (CurrentBar < 20)
      return;

  tripleValue = SMA(20)[0] * 3;
  Value[0] = SMA(20)[0];
}

public double TripleValue
{
    get
    {
      //call OnBarUpdate before returning tripleValue
      Update();
      return tripleValue;
    }
}

```