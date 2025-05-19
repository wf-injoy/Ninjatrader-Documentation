## [Definition](https://developer.ninjatrader.com/docs/desktop/simplefont\#definition)

Defines a particular font configuration.

## Note

Note: SimpleFont objects are used for various **Drawing** methods, and can be used when defining UI element for Add-ons.

## [Constructors](https://developer.ninjatrader.com/docs/desktop/simplefont\#constructors)

| **SimpleFont()** | Creates a SimpleFont object using a family name of "Arial" and a size of "12" |
| **SimpleFont(string familyName, int size)** | Creates a SimpleFont object using the specified family name and size |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/simplefont\#methods-and-properties)

| **Bold** | A bool value determining if the Font is bold style |
| **Family** | A **FontFamily** representing a family of Fonts |
| **Italic** | A bool value determining if the Font is italic style |
| **Size** | A **double** value determining the size of font in WPF units (please see the tip below) |
| **Typeface** | A **Typeface** used to represent the variation of the font used |
| **[ApplyTo()](https://developer.ninjatrader.com/docs/desktop/applyto)** | Applies a custom [SimpleFont](https://developer.ninjatrader.com/docs/desktop/simplefont) object's properties (family, size, and style) to a [Windows Control](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control?view=windowsdesktop-9.0&redirectedfrom=MSDN) |
| **[ToDirectWriteTextFormat()](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat)** | Converts a SimpleFont object to a SharpDX compatible font which can be used for chart rendering. |

## Note

The WPF unit used is the default px one, so device independent pixels. With a default system DPI setting of 96, the physical pixel on the screen would be identical in size, but can vary if a custom DPI is employed. Both should not be confused with the points based font sizing known from other familiar Windows applications like Word, the advantage here is that the non points based size measurement will increase / decrease in size if the system DPI is changed - a more detailed discussion is located [here](https://blogs.msdn.microsoft.com/text/2009/12/11/wpf-text-measurement-units/).

## [Examples](https://developer.ninjatrader.com/docs/desktop/simplefont\#examples)

```jsx-150469391 csharp
// create custom Courier New, make it big and bold
NinjaTrader.Gui.Tools.SimpleFont myFont = new NinjaTrader.Gui.Tools.SimpleFont("Courier New", 12) { Size = 50, Bold = true };

Draw.Text(this, "myTag", false, "Hi There!", 0, Low[0], 5, Brushes.Blue, myFont, TextAlignment.Center, Brushes.Black, null, 1);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/simplefont\#definition)

Defines a particular font configuration.

## Note

Note: SimpleFont objects are used for various **Drawing** methods, and can be used when defining UI element for Add-ons.

## [Constructors](https://developer.ninjatrader.com/docs/desktop/simplefont\#constructors)

| **SimpleFont()** | Creates a SimpleFont object using a family name of "Arial" and a size of "12" |
| **SimpleFont(string familyName, int size)** | Creates a SimpleFont object using the specified family name and size |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/simplefont\#methods-and-properties)

| **Bold** | A bool value determining if the Font is bold style |
| **Family** | A **FontFamily** representing a family of Fonts |
| **Italic** | A bool value determining if the Font is italic style |
| **Size** | A **double** value determining the size of font in WPF units (please see the tip below) |
| **Typeface** | A **Typeface** used to represent the variation of the font used |
| **[ApplyTo()](https://developer.ninjatrader.com/docs/desktop/applyto)** | Applies a custom [SimpleFont](https://developer.ninjatrader.com/docs/desktop/simplefont) object's properties (family, size, and style) to a [Windows Control](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control?view=windowsdesktop-9.0&redirectedfrom=MSDN) |
| **[ToDirectWriteTextFormat()](https://developer.ninjatrader.com/docs/desktop/todirectwritetextformat)** | Converts a SimpleFont object to a SharpDX compatible font which can be used for chart rendering. |

## Note

The WPF unit used is the default px one, so device independent pixels. With a default system DPI setting of 96, the physical pixel on the screen would be identical in size, but can vary if a custom DPI is employed. Both should not be confused with the points based font sizing known from other familiar Windows applications like Word, the advantage here is that the non points based size measurement will increase / decrease in size if the system DPI is changed - a more detailed discussion is located [here](https://blogs.msdn.microsoft.com/text/2009/12/11/wpf-text-measurement-units/).

## [Examples](https://developer.ninjatrader.com/docs/desktop/simplefont\#examples)

```jsx-150469391 csharp
// create custom Courier New, make it big and bold
NinjaTrader.Gui.Tools.SimpleFont myFont = new NinjaTrader.Gui.Tools.SimpleFont("Courier New", 12) { Size = 50, Bold = true };

Draw.Text(this, "myTag", false, "Hi There!", 0, Low[0], 5, Brushes.Blue, myFont, TextAlignment.Center, Brushes.Black, null, 1);

```