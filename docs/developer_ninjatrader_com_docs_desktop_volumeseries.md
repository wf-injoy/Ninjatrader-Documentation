## [Definition](https://developer.ninjatrader.com/docs/desktop/volumeseries\#definition)

Represents historical volume data as ISeries< `double` \> interface which can be used for custom NinjaScript object calculations

## Note

In most cases, you will access the historical volume series using a core event handler such as OnBarUpdate.  For more advance developers, you may find situations where you wish to access historical volume series outside of the core event methods, such as your own custom mouse click.  In these advanced scenarios, you may run into situations where the barsAgo pointer is not in sync with the current bar, which may cause errors when trying to obtain this information.  In those cases, use the Bars.Get...() methods with the absolute bar index, e.g., [Bars.GetVolume()](https://developer.ninjatrader.com/docs/desktop/getvolume).

## [Single ISeries< `double` >](https://developer.ninjatrader.com/docs/desktop/volumeseries\#single-iseries%3C-%3E)

| [Volume](https://developer.ninjatrader.com/docs/desktop/volume) | A collection of historical bar volume values. |

## [Multi-Time Frame ISeries< `double` >](https://developer.ninjatrader.com/docs/desktop/volumeseries\#multi-time-frame-iseries%3C-%3E)

| [Volumes](https://developer.ninjatrader.com/docs/desktop/volumes) | Holds an array of ISeries< `double` \> objects holding historical bar volume. |

## [Definition](https://developer.ninjatrader.com/docs/desktop/volumeseries\#definition)

Represents historical volume data as ISeries< `double` \> interface which can be used for custom NinjaScript object calculations

## Note

In most cases, you will access the historical volume series using a core event handler such as OnBarUpdate.  For more advance developers, you may find situations where you wish to access historical volume series outside of the core event methods, such as your own custom mouse click.  In these advanced scenarios, you may run into situations where the barsAgo pointer is not in sync with the current bar, which may cause errors when trying to obtain this information.  In those cases, use the Bars.Get...() methods with the absolute bar index, e.g., [Bars.GetVolume()](https://developer.ninjatrader.com/docs/desktop/getvolume).

## [Single ISeries< `double` >](https://developer.ninjatrader.com/docs/desktop/volumeseries\#single-iseries%3C-%3E)

| [Volume](https://developer.ninjatrader.com/docs/desktop/volume) | A collection of historical bar volume values. |

## [Multi-Time Frame ISeries< `double` >](https://developer.ninjatrader.com/docs/desktop/volumeseries\#multi-time-frame-iseries%3C-%3E)

| [Volumes](https://developer.ninjatrader.com/docs/desktop/volumes) | Holds an array of ISeries< `double` \> objects holding historical bar volume. |