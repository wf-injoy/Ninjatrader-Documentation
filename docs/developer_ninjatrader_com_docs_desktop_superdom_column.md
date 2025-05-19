Custom SuperDOM Columns can be used to add additional functionality to the **SuperDOM** window. The methods and properties covered in this section are unique to custom SuperDOM column development.

## [In this section](https://developer.ninjatrader.com/docs/desktop/superdom_column\#in-this-section)

| Method | Description |
| --- | --- |
| [MarketDepth](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth) | Provides Level 2 information for a SuperDOMColumn. |
| [OnMarketData()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata) | Called and guaranteed to be in the correct sequence for every change in level one market data for the underlying instrument. The **OnMarketData()** method updates can include but is not limited to the bid, ask, last price and volume. |
| [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate) | Called every time an **order** changes state. An order will change state when a change in order quantity, price or state (e.g. working to filled) occurs. |
| [OnPositionUpdate()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onpositionupdate) | Called every time a **position** changes state. |
| [OnPropertyChanged()](https://developer.ninjatrader.com/docs/desktop/onpropertychanged) | This method should be used any time you wish to repaint the column instead of calling **OnRender()** directly. |
| [OnRender()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onrender) | Used to draw custom content to the SuperDOM Column, such as a Grid. |
| [OnRestoreValues()](https://developer.ninjatrader.com/docs/desktop/onrestorevalues) | Called when the column is restored (e.g. from a workspace). |

Custom SuperDOM Columns can be used to add additional functionality to the **SuperDOM** window. The methods and properties covered in this section are unique to custom SuperDOM column development.

## [In this section](https://developer.ninjatrader.com/docs/desktop/superdom_column\#in-this-section)

| Method | Description |
| --- | --- |
| [MarketDepth](https://developer.ninjatrader.com/docs/desktop/superdom_marketdepth) | Provides Level 2 information for a SuperDOMColumn. |
| [OnMarketData()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onmarketdata) | Called and guaranteed to be in the correct sequence for every change in level one market data for the underlying instrument. The **OnMarketData()** method updates can include but is not limited to the bid, ask, last price and volume. |
| [OnOrderUpdate()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onorderupdate) | Called every time an **order** changes state. An order will change state when a change in order quantity, price or state (e.g. working to filled) occurs. |
| [OnPositionUpdate()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onpositionupdate) | Called every time a **position** changes state. |
| [OnPropertyChanged()](https://developer.ninjatrader.com/docs/desktop/onpropertychanged) | This method should be used any time you wish to repaint the column instead of calling **OnRender()** directly. |
| [OnRender()](https://developer.ninjatrader.com/docs/desktop/superdomcolumn_onrender) | Used to draw custom content to the SuperDOM Column, such as a Grid. |
| [OnRestoreValues()](https://developer.ninjatrader.com/docs/desktop/onrestorevalues) | Called when the column is restored (e.g. from a workspace). |