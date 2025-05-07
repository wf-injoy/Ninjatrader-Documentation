## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#definition)

The `TextLayout` interface represents a block of text after it has been fully analyzed and formatted.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316718.aspx))

## Note

To draw a formatted string represented by a **TextLayout** object, Direct2D provides the **DrawTextLayout** method.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#syntax)

`class TextLayout`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#constructors)

| Constructor | Description |
| --- | --- |
| `new ` TextLayout(Factory factory, string text, [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat) textFormat, float maxWidth, float maxHeight) | Takes a string, text format, and associated constraints, and produces an object that represents the fully analyzed and formatted result. |

## Note

Tip: For NinjaScript development purposes, when creating a **TextLayout** object you should use the [**NinjaTrader.Core.Globals.DirectWriteFactory**](https://developer.ninjatrader.com/docs/desktop/directwritefactory) property.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [**Dispose()**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [**FlowDirection**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_flowdirection) | Gets or sets the direction that text lines flow. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontFamilyName**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontfamilyname) | Gets a copy of the font family name. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontSize**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontsize) | Gets the font size in DIP units. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontStretch**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontstretch) | Gets the font stretch of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontStyle**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontstyle) | Gets the font style of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontWeight**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontweight) | Gets the font weight of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**IsDisposed**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [**MaxHeight**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_maxheight) | Gets or sets the layout maximum height. |
| [**MaxWidth**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_maxwidth) | Gets or sets the layout maximum width. |
| [**Metrics**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics) | Contains the metrics associated with text after layout. All coordinates are in device independent pixels (DIPs). |
| [**ParagraphAlignment**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_paragraphalignment) | Gets or sets the alignment option of a paragraph which is relative to the top and bottom edges of a layout box. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**ReadingDirection**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_readingdirection) | Gets or sets the current reading direction for text in a paragraph. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**TextAlignment**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_textalignment) | Gets or sets the alignment option of text relative to the layout box's leading and trailing edge. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**WordWrapping**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_wordwrapping) | Gets or sets the word wrapping option. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#definition)

The `TextLayout` interface represents a block of text after it has been fully analyzed and formatted.

(See also [unmanaged API documentation](http://msdn.microsoft.com/en-us/library/dd316718.aspx))

## Note

To draw a formatted string represented by a **TextLayout** object, Direct2D provides the **DrawTextLayout** method.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#syntax)

`class TextLayout`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#constructors)

| Constructor | Description |
| --- | --- |
| `new ` TextLayout(Factory factory, string text, [TextFormat](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat) textFormat, float maxWidth, float maxHeight) | Takes a string, text format, and associated constraints, and produces an object that represents the fully analyzed and formatted result. |

## Note

Tip: For NinjaScript development purposes, when creating a **TextLayout** object you should use the [**NinjaTrader.Core.Globals.DirectWriteFactory**](https://developer.ninjatrader.com/docs/desktop/directwritefactory) property.

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout\#methods-and-properties)

| Method/Property | Description |
| --- | --- |
| [**Dispose()**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_dispose) | Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [**FlowDirection**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_flowdirection) | Gets or sets the direction that text lines flow. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontFamilyName**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontfamilyname) | Gets a copy of the font family name. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontSize**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontsize) | Gets the font size in DIP units. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontStretch**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontstretch) | Gets the font stretch of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontStyle**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontstyle) | Gets the font style of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**FontWeight**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_fontweight) | Gets the font weight of the text. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**IsDisposed**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase_isdisposed) | Gets a value indicating whether this instance is disposed. (Inherited from [**SharpDX.DisposeBase**](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase).) |
| [**MaxHeight**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_maxheight) | Gets or sets the layout maximum height. |
| [**MaxWidth**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_maxwidth) | Gets or sets the layout maximum width. |
| [**Metrics**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics) | Contains the metrics associated with text after layout. All coordinates are in device independent pixels (DIPs). |
| [**ParagraphAlignment**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_paragraphalignment) | Gets or sets the alignment option of a paragraph which is relative to the top and bottom edges of a layout box. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**ReadingDirection**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_readingdirection) | Gets or sets the current reading direction for text in a paragraph. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**TextAlignment**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_textalignment) | Gets or sets the alignment option of text relative to the layout box's leading and trailing edge. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |
| [**WordWrapping**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat_wordwrapping) | Gets or sets the word wrapping option. (Inherited from [**TextFormat**](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textformat).) |