The methods and properties covered in this section are unique to custom indicator development. Indicator configuration properties globally define various behaviors of indicators. All properties have default values and can be overridden by setting them in the **OnStateChange()** method of the indicator.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/indicator\#methods-and-properties)

| Method | Description |
| --- | --- |
| [AddLine()](https://developer.ninjatrader.com/docs/desktop/addline) | Adds line objects on a chart. |
| [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) | Adds plot objects that define how an indicator or strategy data series render on a chart. |
| [BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot) | The number of bars on a chart required before the script plots. |
| [DisplayInDataBox](https://developer.ninjatrader.com/docs/desktop/displayindatabox) | Determines if plot(s) display in the chart data box. |
| [DrawHorizontalGridLines](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines) | Plots horizontal grid lines on the indicator panel. |
| [DrawOnPricePanel](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel) | Determines the chart panel the draw objects renders. |
| [DrawVerticalGridLines](https://developer.ninjatrader.com/docs/desktop/drawverticalgridlines) | Plots vertical grid lines on the indicator panel. |
| [IndicatorBaseConverter](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter) | A custom TypeConverter class handling the designed behavior of an indicator's property descriptor collection. |
| [IsChartOnly](https://developer.ninjatrader.com/docs/desktop/ischartonly) | If true, any indicator will be only available for charting usage - indicators with this property enabled would for example not be expected to show if called in a SuperDOM or MarketAnalyzer window. |
| [IsSuspendedWhileInactive](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive) | Prevents real-time market data events from being raised while the indicator's hosting feature is in a state that would be considered suspended and not in immediate use by a user. |
| [PaintPriceMarkers](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers) | If true, any indicator plot values display price markers in the y-axis. |
| [ShowTransparentPlotsInDataBox](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox) | Determines if plot(s) values which are set to a Transparent brush display in the chart data box. |

The methods and properties covered in this section are unique to custom indicator development. Indicator configuration properties globally define various behaviors of indicators. All properties have default values and can be overridden by setting them in the **OnStateChange()** method of the indicator.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/indicator\#methods-and-properties)

| Method | Description |
| --- | --- |
| [AddLine()](https://developer.ninjatrader.com/docs/desktop/addline) | Adds line objects on a chart. |
| [AddPlot()](https://developer.ninjatrader.com/docs/desktop/addplot) | Adds plot objects that define how an indicator or strategy data series render on a chart. |
| [BarsRequiredToPlot](https://developer.ninjatrader.com/docs/desktop/barsrequiredtoplot) | The number of bars on a chart required before the script plots. |
| [DisplayInDataBox](https://developer.ninjatrader.com/docs/desktop/displayindatabox) | Determines if plot(s) display in the chart data box. |
| [DrawHorizontalGridLines](https://developer.ninjatrader.com/docs/desktop/drawhorizontalgridlines) | Plots horizontal grid lines on the indicator panel. |
| [DrawOnPricePanel](https://developer.ninjatrader.com/docs/desktop/drawonpricepanel) | Determines the chart panel the draw objects renders. |
| [DrawVerticalGridLines](https://developer.ninjatrader.com/docs/desktop/drawverticalgridlines) | Plots vertical grid lines on the indicator panel. |
| [IndicatorBaseConverter](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter) | A custom TypeConverter class handling the designed behavior of an indicator's property descriptor collection. |
| [IsChartOnly](https://developer.ninjatrader.com/docs/desktop/ischartonly) | If true, any indicator will be only available for charting usage - indicators with this property enabled would for example not be expected to show if called in a SuperDOM or MarketAnalyzer window. |
| [IsSuspendedWhileInactive](https://developer.ninjatrader.com/docs/desktop/issuspendedwhileinactive) | Prevents real-time market data events from being raised while the indicator's hosting feature is in a state that would be considered suspended and not in immediate use by a user. |
| [PaintPriceMarkers](https://developer.ninjatrader.com/docs/desktop/paintpricemarkers) | If true, any indicator plot values display price markers in the y-axis. |
| [ShowTransparentPlotsInDataBox](https://developer.ninjatrader.com/docs/desktop/showtransparentplotsindatabox) | Determines if plot(s) values which are set to a Transparent brush display in the chart data box. |