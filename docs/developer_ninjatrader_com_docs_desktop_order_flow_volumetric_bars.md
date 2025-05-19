## [Description](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#description)

NinjaTrader Order Flow Volumetric bars provide a detailed ‘x-ray’ view into each price bar’s aggressive buying and selling activity. This technique primarily attempts to answer the question which side was the most aggressive at each price level. This is done by calculating the delta (greek for difference) between buying and selling volume.

Many of the NinjaTrader Order Flow Volumetric Bar and Bar Statistics values could be accessed from your custom NinjaScript objects further leveraging the power of these analysis techniques.

## [Methods and Properties the VolumetricBarsType exposes](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#methods-and-properties-the-volumetricbarstype-exposes)

| Parameter | Description |
| --- | --- |
| BarDelta | Gets a long value with the total bar's delta |
| CumulativeDelta | Gets a long value with the cumulative delta (Note: the accumulation is reset at the session break) |
| DeltaSh | The delta since last time price touched the high of the bar, usually negative |
| DeltaSl | The delta since last time price touched the low of the bar, usually positive. |
| GetAskVolumeForPrice(double price) | Gets the ask volume (long value) for the passed in price |
| GetBidVolumeForPrice(double price) | Gets the sell volume (long value) for the passed in price |
| GetDeltaForPrice(double price) | Gets the horizontal delta (long value) for the passed in price |
| GetDeltaPercent() | Gets A double value with the delta % of volume for the bar |
| GetMaximumPositiveDelta() | Gets the highest positive delta (long value) for the bar (if there is no positive delta in the bar, it will get the lowest negative delta) |
| GetMaximumNegativeDelta() | Gets the highest negative delta (long value) for the bar (if there is no negative delta in the bar, it will get the lowest positive delta) |
| GetMaximumVolume(bool? askVolume, out double price) | Gets the highest Ask, Bid or combined volume (long value) for the bar and returns the price at which it occurred.<br>- pass in true for getting the highest Ask volume<br>  <br>- pass in false for getting the highest Bid volume<br>  <br>- pass in null for getting the highest combined volume<br>  <br>- For scenarios where Ticks per level is greater than 1, this method will return the lowest price - with Ticks per level known, the remaining prices in the result cell could be custom calculated if desired. |
| GetTotalVolumeForPrice(double price) | Gets the total volume (long value) for the passed in price |
| MaxSeenDelta | Gets the highest delta (long value) seen intrabar |
| MinSeenDelta | Gets the lowest delta (long value) seen intrabar |
| TotalBuyingVolume | Gets the total buying volume (long value) for the bar |
| TotalSellingVolume | Gets the total selling volume (long value) for the bar |
| Trades | Gets to total number of trades (long value) for the bar |

## [Examples](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (Bars == null)
        return;

    // This sample assumes the Volumetric series is the primary DataSeries on the chart, if you would want to add a Volumetric series to a
    // script, you could call AddVolumetric() in State.Configure and then for example use
    // NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType barsType = BarsArray[1].BarsType as
    // NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType;

    NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType barsType = Bars.BarsSeries.BarsType as
        NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType;

    if (barsType == null)
        return;

    try
    {
        double price;
        Print("=========================================================================");
        Print("Bar: " + CurrentBar);
        Print("Trades: " + barsType.Volumes[CurrentBar].Trades);
        Print("Total Volume: " + barsType.Volumes[CurrentBar].TotalVolume);
        Print("Total Buying Volume: " + barsType.Volumes[CurrentBar].TotalBuyingVolume);
        Print("Total Selling Volume: " + barsType.Volumes[CurrentBar].TotalSellingVolume);
        Print("Delta for bar: " + barsType.Volumes[CurrentBar].BarDelta);
        Print("Delta for bar (%): " + barsType.Volumes[CurrentBar].GetDeltaPercent());
        Print("Delta for Close: " + barsType.Volumes[CurrentBar].GetDeltaForPrice(Close[0]));
        Print("Ask for Close: " + barsType.Volumes[CurrentBar].GetAskVolumeForPrice(Close[0]));
        Print("Bid for Close: " + barsType.Volumes[CurrentBar].GetBidVolumeForPrice(Close[0]));
        Print("Volume for Close: " + barsType.Volumes[CurrentBar].GetTotalVolumeForPrice(Close[0]));
        Print("Maximum Ask: " + barsType.Volumes[CurrentBar].GetMaximumVolume(true, out price) + " at price: " + price);
        Print("Maximum Bid: " + barsType.Volumes[CurrentBar].GetMaximumVolume(false, out price) + " at price: " + price);
        Print("Maximum Combined: " + barsType.Volumes[CurrentBar].GetMaximumVolume(null, out price) + " at price: " + price);
        Print("Maximum Positive Delta: " + barsType.Volumes[CurrentBar].GetMaximumPositiveDelta());
        Print("Maximum Negative Delta: " + barsType.Volumes[CurrentBar].GetMaximumNegativeDelta());
        Print("Max seen delta (bar): " + barsType.Volumes[CurrentBar].MaxSeenDelta);
        Print("Min seen delta (bar): " + barsType.Volumes[CurrentBar].MinSeenDelta);
        Print("Cumulative delta (bar): " + barsType.Volumes[CurrentBar].CumulativeDelta);
        Print("Delta Since High (bar): " + barsType.Volumes[CurrentBar].DeltaSh);
        Print("Delta Since Low (bar): " + barsType.Volumes[CurrentBar].DeltaSl);
    }
    catch{}
}

```

## Note

Please note in the example above a **CurrentBar** reference is used as index, and not a BarsAgo reference.

## [Description](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#description)

NinjaTrader Order Flow Volumetric bars provide a detailed ‘x-ray’ view into each price bar’s aggressive buying and selling activity. This technique primarily attempts to answer the question which side was the most aggressive at each price level. This is done by calculating the delta (greek for difference) between buying and selling volume.

Many of the NinjaTrader Order Flow Volumetric Bar and Bar Statistics values could be accessed from your custom NinjaScript objects further leveraging the power of these analysis techniques.

## [Methods and Properties the VolumetricBarsType exposes](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#methods-and-properties-the-volumetricbarstype-exposes)

| Parameter | Description |
| --- | --- |
| BarDelta | Gets a long value with the total bar's delta |
| CumulativeDelta | Gets a long value with the cumulative delta (Note: the accumulation is reset at the session break) |
| DeltaSh | The delta since last time price touched the high of the bar, usually negative |
| DeltaSl | The delta since last time price touched the low of the bar, usually positive. |
| GetAskVolumeForPrice(double price) | Gets the ask volume (long value) for the passed in price |
| GetBidVolumeForPrice(double price) | Gets the sell volume (long value) for the passed in price |
| GetDeltaForPrice(double price) | Gets the horizontal delta (long value) for the passed in price |
| GetDeltaPercent() | Gets A double value with the delta % of volume for the bar |
| GetMaximumPositiveDelta() | Gets the highest positive delta (long value) for the bar (if there is no positive delta in the bar, it will get the lowest negative delta) |
| GetMaximumNegativeDelta() | Gets the highest negative delta (long value) for the bar (if there is no negative delta in the bar, it will get the lowest positive delta) |
| GetMaximumVolume(bool? askVolume, out double price) | Gets the highest Ask, Bid or combined volume (long value) for the bar and returns the price at which it occurred.<br>- pass in true for getting the highest Ask volume<br>  <br>- pass in false for getting the highest Bid volume<br>  <br>- pass in null for getting the highest combined volume<br>  <br>- For scenarios where Ticks per level is greater than 1, this method will return the lowest price - with Ticks per level known, the remaining prices in the result cell could be custom calculated if desired. |
| GetTotalVolumeForPrice(double price) | Gets the total volume (long value) for the passed in price |
| MaxSeenDelta | Gets the highest delta (long value) seen intrabar |
| MinSeenDelta | Gets the lowest delta (long value) seen intrabar |
| TotalBuyingVolume | Gets the total buying volume (long value) for the bar |
| TotalSellingVolume | Gets the total selling volume (long value) for the bar |
| Trades | Gets to total number of trades (long value) for the bar |

## [Examples](https://developer.ninjatrader.com/docs/desktop/order_flow_volumetric_bars\#examples)

```jsx-150469391 csharp
protected override void OnBarUpdate()
{
    if (Bars == null)
        return;

    // This sample assumes the Volumetric series is the primary DataSeries on the chart, if you would want to add a Volumetric series to a
    // script, you could call AddVolumetric() in State.Configure and then for example use
    // NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType barsType = BarsArray[1].BarsType as
    // NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType;

    NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType barsType = Bars.BarsSeries.BarsType as
        NinjaTrader.NinjaScript.BarsTypes.VolumetricBarsType;

    if (barsType == null)
        return;

    try
    {
        double price;
        Print("=========================================================================");
        Print("Bar: " + CurrentBar);
        Print("Trades: " + barsType.Volumes[CurrentBar].Trades);
        Print("Total Volume: " + barsType.Volumes[CurrentBar].TotalVolume);
        Print("Total Buying Volume: " + barsType.Volumes[CurrentBar].TotalBuyingVolume);
        Print("Total Selling Volume: " + barsType.Volumes[CurrentBar].TotalSellingVolume);
        Print("Delta for bar: " + barsType.Volumes[CurrentBar].BarDelta);
        Print("Delta for bar (%): " + barsType.Volumes[CurrentBar].GetDeltaPercent());
        Print("Delta for Close: " + barsType.Volumes[CurrentBar].GetDeltaForPrice(Close[0]));
        Print("Ask for Close: " + barsType.Volumes[CurrentBar].GetAskVolumeForPrice(Close[0]));
        Print("Bid for Close: " + barsType.Volumes[CurrentBar].GetBidVolumeForPrice(Close[0]));
        Print("Volume for Close: " + barsType.Volumes[CurrentBar].GetTotalVolumeForPrice(Close[0]));
        Print("Maximum Ask: " + barsType.Volumes[CurrentBar].GetMaximumVolume(true, out price) + " at price: " + price);
        Print("Maximum Bid: " + barsType.Volumes[CurrentBar].GetMaximumVolume(false, out price) + " at price: " + price);
        Print("Maximum Combined: " + barsType.Volumes[CurrentBar].GetMaximumVolume(null, out price) + " at price: " + price);
        Print("Maximum Positive Delta: " + barsType.Volumes[CurrentBar].GetMaximumPositiveDelta());
        Print("Maximum Negative Delta: " + barsType.Volumes[CurrentBar].GetMaximumNegativeDelta());
        Print("Max seen delta (bar): " + barsType.Volumes[CurrentBar].MaxSeenDelta);
        Print("Min seen delta (bar): " + barsType.Volumes[CurrentBar].MinSeenDelta);
        Print("Cumulative delta (bar): " + barsType.Volumes[CurrentBar].CumulativeDelta);
        Print("Delta Since High (bar): " + barsType.Volumes[CurrentBar].DeltaSh);
        Print("Delta Since Low (bar): " + barsType.Volumes[CurrentBar].DeltaSl);
    }
    catch{}
}

```

## Note

Please note in the example above a **CurrentBar** reference is used as index, and not a BarsAgo reference.