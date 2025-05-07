## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#definition)

Contains the metrics associated with text after layout. All coordinates are in device independent pixels (DIPs).

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd368135.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#syntax)

`<textlayout>.Metrics`

## [Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#properties)

| Property | Description |
| --- | --- |
| Left | A float value that indicates the left-most point of formatted text relative to the layout box, while excluding any glyph overhang. |
| Top | A float value that indicates the top-most point of formatted text relative to the layout box, while excluding any glyph overhang. |
| Width | A float value that indicates the width of the formatted text, while ignoring trailing whitespace at the end of each line. |
| WidthIncludingTrailingWhitespace | A float value that indicates width of the formatted text, taking into account the trailing whitespace at the end of each line. |
| Height | A float value that indicates the height of the formatted text. The height of an empty string is set to the same value as that of the default font. |
| LayoutWidth | A float value that indicates the initial width given to the layout. It can be either larger or smaller than the text content width, depending on whether the text was wrapped. |
| LayoutHeight | A float value that indicates the initial height given to the layout. Depending on the length of the text, it may be larger or smaller than the text content height. |
| MaxBidiReorderingDepth | An **int** value representing the maximum reordering count of any line of text, used to calculate the most number of hit-testing boxes needed. If the layout has no bidirectional text, or no text at all, the minimum level is 1. |
| LineCount | An **int** value representing total number of lines. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#definition)

Contains the metrics associated with text after layout. All coordinates are in device independent pixels (DIPs).

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd368135.aspx))

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#syntax)

`<textlayout>.Metrics`

## [Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_directwrite_textlayout_metrics\#properties)

| Property | Description |
| --- | --- |
| Left | A float value that indicates the left-most point of formatted text relative to the layout box, while excluding any glyph overhang. |
| Top | A float value that indicates the top-most point of formatted text relative to the layout box, while excluding any glyph overhang. |
| Width | A float value that indicates the width of the formatted text, while ignoring trailing whitespace at the end of each line. |
| WidthIncludingTrailingWhitespace | A float value that indicates width of the formatted text, taking into account the trailing whitespace at the end of each line. |
| Height | A float value that indicates the height of the formatted text. The height of an empty string is set to the same value as that of the default font. |
| LayoutWidth | A float value that indicates the initial width given to the layout. It can be either larger or smaller than the text content width, depending on whether the text was wrapped. |
| LayoutHeight | A float value that indicates the initial height given to the layout. Depending on the length of the text, it may be larger or smaller than the text content height. |
| MaxBidiReorderingDepth | An **int** value representing the maximum reordering count of any line of text, used to calculate the most number of hit-testing boxes needed. If the layout has no bidirectional text, or no text at all, the minimum level is 1. |
| LineCount | An **int** value representing total number of lines. |