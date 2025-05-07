## [Definition](https://developer.ninjatrader.com/docs/desktop/priceseries\#definition)

Represents historical data as an **ISeries `<double>`** interface which can be used for custom NinjaScript object calculations.

## Note

In most cases, you will access the historical price series using a core event handler such as **OnBarUpdate**. For more advanced developers, you may find situations where you wish to access historical price series outside of the core event methods, such as your own custom mouse click. In these advanced scenarios, you may run into situations where the **barsAgo** pointer is not in sync with the current bar, which may cause errors when trying to obtain this information. In those cases, please use the **Bars.Get...()** methods with the absolute bar index, e.g., [**Bars.GetClose()**](https://developer.ninjatrader.com/docs/desktop/getclose), [**Bars.GetOpen()**](https://developer.ninjatrader.com/docs/desktop/getopen), etc.

## [Single ISeries `<double>`](https://developer.ninjatrader.com/docs/desktop/priceseries\#single-iseries)

| [Close](https://developer.ninjatrader.com/docs/desktop/close) | A collection of historical bar close prices. |
| [High](https://developer.ninjatrader.com/docs/desktop/high) | A collection of historical bar high prices. |
| [Input](https://developer.ninjatrader.com/docs/desktop/input) | A collect of the the main historical input values. |
| [Low](https://developer.ninjatrader.com/docs/desktop/low) | A collection of historical bar low prices. |
| [Median](https://developer.ninjatrader.com/docs/desktop/median) | A collection of historical bar median prices. |
| [Open](https://developer.ninjatrader.com/docs/desktop/open) | A collection of historical bar open prices. |
| [Typical](https://developer.ninjatrader.com/docs/desktop/typical) | A collection of historical bar typical prices. |
| [Value](https://developer.ninjatrader.com/docs/desktop/value) | A collection of historical references to the first object ( **Values\[0\]**) in the indicator. |
| [Weighted](https://developer.ninjatrader.com/docs/desktop/weighted) | A collection of historical bar weighted prices. |

## [Multi-Time Frame ISeries `<double>`](https://developer.ninjatrader.com/docs/desktop/priceseries\#multi-time-frame-iseries)

| [Closes](https://developer.ninjatrader.com/docs/desktop/closes) | Holds an array of **ISeries `<double>`** objects holding historical bar close prices. |
| [Highs](https://developer.ninjatrader.com/docs/desktop/highs) | Holds an array of **ISeries `<double>`** objects holding historical bar high prices. |
| [Inputs](https://developer.ninjatrader.com/docs/desktop/inputs) | Holds an array of **ISeries `<double>`** objects holding main historical input values. |
| [Lows](https://developer.ninjatrader.com/docs/desktop/lows) | Holds an array of **ISeries `<double>`** objects holding historical bar low prices. |
| [Medians](https://developer.ninjatrader.com/docs/desktop/medians) | Holds an array of **ISeries `<double>`** objects holding historical bar median prices. |
| [Opens](https://developer.ninjatrader.com/docs/desktop/opens) | Holds an array of **ISeries `<double>`** objects holding historical bar open prices. |
| [Typicals](https://developer.ninjatrader.com/docs/desktop/typicals) | Holds an array of **ISeries `<double>`** objects holding historical bar typical prices. |
| [Values](https://developer.ninjatrader.com/docs/desktop/values) | Holds an array of **ISeries `<double>`** objects holding the indicator's underlying calculated values. |
| [Weighteds](https://developer.ninjatrader.com/docs/desktop/weighteds) | Holds an array of **ISeries `<double>`** objects holding historical bar weighted prices. |

## [Definition](https://developer.ninjatrader.com/docs/desktop/priceseries\#definition)

Represents historical data as an **ISeries `<double>`** interface which can be used for custom NinjaScript object calculations.

## Note

In most cases, you will access the historical price series using a core event handler such as **OnBarUpdate**. For more advanced developers, you may find situations where you wish to access historical price series outside of the core event methods, such as your own custom mouse click. In these advanced scenarios, you may run into situations where the **barsAgo** pointer is not in sync with the current bar, which may cause errors when trying to obtain this information. In those cases, please use the **Bars.Get...()** methods with the absolute bar index, e.g., [**Bars.GetClose()**](https://developer.ninjatrader.com/docs/desktop/getclose), [**Bars.GetOpen()**](https://developer.ninjatrader.com/docs/desktop/getopen), etc.

## [Single ISeries `<double>`](https://developer.ninjatrader.com/docs/desktop/priceseries\#single-iseries)

| [Close](https://developer.ninjatrader.com/docs/desktop/close) | A collection of historical bar close prices. |
| [High](https://developer.ninjatrader.com/docs/desktop/high) | A collection of historical bar high prices. |
| [Input](https://developer.ninjatrader.com/docs/desktop/input) | A collect of the the main historical input values. |
| [Low](https://developer.ninjatrader.com/docs/desktop/low) | A collection of historical bar low prices. |
| [Median](https://developer.ninjatrader.com/docs/desktop/median) | A collection of historical bar median prices. |
| [Open](https://developer.ninjatrader.com/docs/desktop/open) | A collection of historical bar open prices. |
| [Typical](https://developer.ninjatrader.com/docs/desktop/typical) | A collection of historical bar typical prices. |
| [Value](https://developer.ninjatrader.com/docs/desktop/value) | A collection of historical references to the first object ( **Values\[0\]**) in the indicator. |
| [Weighted](https://developer.ninjatrader.com/docs/desktop/weighted) | A collection of historical bar weighted prices. |

## [Multi-Time Frame ISeries `<double>`](https://developer.ninjatrader.com/docs/desktop/priceseries\#multi-time-frame-iseries)

| [Closes](https://developer.ninjatrader.com/docs/desktop/closes) | Holds an array of **ISeries `<double>`** objects holding historical bar close prices. |
| [Highs](https://developer.ninjatrader.com/docs/desktop/highs) | Holds an array of **ISeries `<double>`** objects holding historical bar high prices. |
| [Inputs](https://developer.ninjatrader.com/docs/desktop/inputs) | Holds an array of **ISeries `<double>`** objects holding main historical input values. |
| [Lows](https://developer.ninjatrader.com/docs/desktop/lows) | Holds an array of **ISeries `<double>`** objects holding historical bar low prices. |
| [Medians](https://developer.ninjatrader.com/docs/desktop/medians) | Holds an array of **ISeries `<double>`** objects holding historical bar median prices. |
| [Opens](https://developer.ninjatrader.com/docs/desktop/opens) | Holds an array of **ISeries `<double>`** objects holding historical bar open prices. |
| [Typicals](https://developer.ninjatrader.com/docs/desktop/typicals) | Holds an array of **ISeries `<double>`** objects holding historical bar typical prices. |
| [Values](https://developer.ninjatrader.com/docs/desktop/values) | Holds an array of **ISeries `<double>`** objects holding the indicator's underlying calculated values. |
| [Weighteds](https://developer.ninjatrader.com/docs/desktop/weighteds) | Holds an array of **ISeries `<double>`** objects holding historical bar weighted prices. |