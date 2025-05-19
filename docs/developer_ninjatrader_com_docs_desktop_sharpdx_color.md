## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#definition)

Represents a 32-bit color (4 bytes) in the form of RGBA (in byte order: R, G, B, A).

## Note

Notes:

1. The color of each pixel is represented as a 32-bit number: 8 bits each for alpha, red, green, and blue (ARGB). Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity. The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque. To determine the alpha, red, green, or blue component of a color, use the **A**, **R**, **G**, or **B** property, respectively.
2. Named colors are represented by using the properties of the Color structure. Please see the table of Static Named Colors below.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#syntax)

`struct Color`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#constructors)

| Constructor | Description |
| --- | --- |
| `new Color()` | Initializes a new instance of the `Color` struct |
| `new Color(float red, float green, float blue)` | Initializes a new instance of the **Color** struct using float values |
| new `Color(float red, float green, float blue, float alpha)` Inializes a new instance of the **Color** struct using float values with alpha transparency |
| `new Color(int red, int green, int blue)` | Initializes a new instance of the **Color** struct using int values |
| `new Color(int red, int green, int blue, int alpha)` | Initializes a new instance of the **Color** struct using int values with alpha transparency |
| `new Color(byte red, byte green, byte blue)` | Initializes a new instance of the **Color** struct using byte values |
| `new Color(byte red, byte green, byte blue, byte alpha)` | Initializes a new instance of the **Color** struct using byte values with alpha transparency |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| **R** | The red component of the color |
| **G** | The green component of the color |
| **B** | The blue component of the color |
| **A** | The alpha component of the color |
| **ToColor3()** | Converts the color into a [three component](https://developer.ninjatrader.com/docs/desktop/sharpdx_color3) color |
| **ToColor4()** | Converts the color into a [four component](https://developer.ninjatrader.com/docs/desktop/sharpdx_color4) color |

## [Static Named Colors](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#static-named-colors)

### Colors by name

| Color Name | Description |
| --- | --- |
| **SharpDX.Color.Zero** | Zero color |
| **SharpDX.Color.Transparent** | Transparent color |
| **SharpDX.Color.AliceBlue** | AliceBlue color |
| **SharpDX.Color.AntiqueWhite** | AntiqueWhite color |
| **SharpDX.Color.Aqua** | Aqua color |
| **SharpDX.Color.Aquamarine** | Aquamarine color |
| **SharpDX.Color.Azure** | Azure color |
| **SharpDX.Color.Beige** | Beige color |
| **SharpDX.Color.Bisque** | Bisque color |
| **SharpDX.Color.Black** | Black color |
| **SharpDX.Color.BlanchedAlmond** | BlanchedAlmond color |
| **SharpDX.Color.Blue** | Blue color |
| **SharpDX.Color.BlueViolet** | BlueViolet color |
| **SharpDX.Color.Brown** | Brown color |
| **SharpDX.Color.BurlyWood** | BurlyWood color |
| **SharpDX.Color.CadetBlue** | CadetBlue color |
| **SharpDX.Color.Chartreuse** | Chartreuse color |
| **SharpDX.Color.Chocolate** | Chocolate color |
| **SharpDX.Color.Coral** | Coral color |
| **SharpDX.Color.CornflowerBlue** | CornflowerBlue color |
| **SharpDX.Color.Cornsilk** | Cornsilk color |
| **SharpDX.Color.Crimson** | Crimson color |
| **SharpDX.Color.Cyan** | Cyan color |
| **SharpDX.Color.DarkBlue** | DarkBlue color |
| **SharpDX.Color.DarkCyan** | DarkCyan color |
| **SharpDX.Color.DarkGoldenrod** | DarkGoldenrod color |
| **SharpDX.Color.DarkGray** | DarkGray color |
| **SharpDX.Color.DarkGreen** | DarkGreen color |
| **SharpDX.Color.DarkKhaki** | DarkKhaki color |
| **SharpDX.Color.DarkMagenta** | DarkMagenta color |
| **SharpDX.Color.DarkOliveGreen** | DarkOliveGreen color |
| **SharpDX.Color.DarkOrange** | DarkOrange color |
| **SharpDX.Color.DarkOrchid** | DarkOrchid color |
| **SharpDX.Color.DarkRed** | DarkRed color |
| **SharpDX.Color.DarkSalmon** | DarkSalmon color |
| **SharpDX.Color.DarkSeaGreen** | DarkSeaGreen color |
| **SharpDX.Color.DarkSlateBlue** | DarkSlateBlue color |
| **SharpDX.Color.DarkSlateGray** | DarkSlateGray color |
| **SharpDX.Color.DarkTurquoise** | DarkTurquoise color |
| **SharpDX.Color.DarkViolet** | DarkViolet color |
| **SharpDX.Color.DeepPink** | DeepPink color |
| **SharpDX.Color.DeepSkyBlue** | DeepSkyBlue color |
| **SharpDX.Color.DimGray** | DimGray color |
| **SharpDX.Color.DodgerBlue** | DodgerBlue color |
| **SharpDX.Color.Firebrick** | Firebrick color |
| **SharpDX.Color.FloralWhite** | FloralWhite color |
| **SharpDX.Color.ForestGreen** | ForestGreen color |
| **SharpDX.Color.Fuchsia** | Fuchsia color |
| **SharpDX.Color.Gainsboro** | Gainsboro color |
| **SharpDX.Color.GhostWhite** | GhostWhite color |
| **SharpDX.Color.Gold** | Gold color |
| **SharpDX.Color.Goldenrod** | Goldenrod color |
| **SharpDX.Color.Gray** | Gray color |
| **SharpDX.Color.Green** | Green color |
| **SharpDX.Color.GreenYellow** | GreenYellow color |
| **SharpDX.Color.Honeydew** | Honeydew color |
| **SharpDX.Color.HotPink** | HotPink color |
| **SharpDX.Color.IndianRed** | IndianRed color |
| **SharpDX.Color.Indigo** | Indigo color |
| **SharpDX.Color.Ivory** | Ivory color |
| **SharpDX.Color.Khaki** | Khaki color |
| **SharpDX.Color.Lavender** | Lavender color |
| **SharpDX.Color.LavenderBlush** | LavenderBlush color |
| **SharpDX.Color.LawnGreen** | LawnGreen color |
| **LemonChiffon** | LemonChiffon color |
| **SharpDX.Color.LightBlue** | LightBlue color |
| **SharpDX.Color.LightCoral** | LightCoral color |
| **SharpDX.Color.LightCyan** | LightCyan color |
| **SharpDX.Color.LightGoldenrodYellow** | LightGoldenrodYellow color |
| **SharpDX.Color.LightGray** | LightGray color |
| **SharpDX.Color.LightGreen** | LightGreen color |
| **SharpDX.Color.LightPink** | LightPink color |
| **SharpDX.Color.LightSalmon** | LightSalmon color |
| **SharpDX.Color.LightSeaGreen** | LightSeaGreen color |
| **SharpDX.Color.LightSkyBlue** | LightSkyBlue color |
| **SharpDX.Color.LightSlateGray** | LightSlateGray color |
| **SharpDX.Color.LightSteelBlue** | LightSteelBlue color |
| **SharpDX.Color.LightYellow** | LightYellow color |
| **SharpDX.Color.Lime** | Lime color |
| **SharpDX.Color.LimeGreen** | LimeGreen color |
| **SharpDX.Color.Linen** | Linen color |
| **SharpDX.Color.Magenta** | Magenta color |
| **SharpDX.Color.Maroon** | Maroon color |
| **SharpDX.Color.MediumAquamarine** | MediumAquamarine color |
| **SharpDX.Color.MediumBlue** | MediumBlue color |
| **SharpDX.Color.MediumOrchid** | MediumOrchid color |
| **SharpDX.Color.MediumPurple** | MediumPurple color |
| **SharpDX.Color.MediumSeaGreen** | MediumSeaGreen color |
| **SharpDX.Color.MediumSlateBlue** | MediumSlateBlue color |
| **SharpDX.Color.MediumSpringGreen** | MediumSpringGreen color |
| **SharpDX.Color.MediumTurquoise** | MediumTurquoise color |
| **SharpDX.Color.MediumVioletRed** | MediumVioletRed color |
| **SharpDX.Color.MidnightBlue** | MidnightBlue color |
| **SharpDX.Color.MintCream** | MintCream color |
| **SharpDX.Color.MistyRose** | MistyRose color |
| **SharpDX.Color.Moccasin** | Moccasin color |
| **SharpDX.Color.NavajoWhite** | NavajoWhite color |
| **SharpDX.Color.Navy** | Navy color |
| **SharpDX.Color.OldLace** | OldLace color |
| **SharpDX.Color.Olive** | Olive color |
| **SharpDX.Color.OliveDrab** | OliveDrab color |
| **SharpDX.Color.Orange** | Orange color |
| **SharpDX.Color.OrangeRed** | OrangeRed color |
| **SharpDX.Color.Orchid** | Orchid color |
| **SharpDX.Color.PaleGoldenrod** | PaleGoldenrod color |
| **SharpDX.Color.PaleGreen** | PaleGreen color |
| **SharpDX.Color.PaleTurquoise** | PaleTurquoise color |
| **SharpDX.Color.PaleVioletRed** | PaleVioletRed color |
| **SharpDX.Color.PapayaWhip** | PapayaWhip color |
| **SharpDX.Color.PeachPuff** | PeachPuff color |
| **SharpDX.Color.Peru** | Peru color |
| **SharpDX.Color.Pink** | Pink color |
| **SharpDX.Color.Plum** | Plum color |
| **SharpDX.Color.PowderBlue** | PowderBlue color |
| **SharpDX.Color.Purple** | Purple color |
| **SharpDX.Color.Red** | Red color |
| **SharpDX.Color.RosyBrown** | RosyBrown color |
| **SharpDX.Color.RoyalBlue** | RoyalBlue color |
| **SharpDX.Color.SaddleBrown** | SaddleBrown color |
| **SharpDX.Color.Salmon** | Salmon color |
| **SharpDX.Color.SandyBrown** | SandyBrown color |
| **SharpDX.Color.SeaGreen** | SeaGreen color |
| **SharpDX.Color.SeaShell** | SeaShell color |
| **SharpDX.Color.Sienna** | Sienna color |
| **SharpDX.Color.Silver** | Silver color |
| **SharpDX.Color.SkyBlue** | SkyBlue color |
| **SharpDX.Color.SlateBlue** | SlateBlue color |
| **SharpDX.Color.SlateGray** | SlateGray color |
| **SharpDX.Color.Snow** | Snow color |
| **SharpDX.Color.SpringGreen** | SpringGreen color |
| **SharpDX.Color.SteelBlue** | SteelBlue color |
| **SharpDX.Color.Tan** | Tan color |
| **SharpDX.Color.Teal** | Teal color |
| **SharpDX.Color.Thistle** | Thistle color |
| **SharpDX.Color.Tomato** | Tomato color |
| **SharpDX.Color.Turquoise** | Turquoise color |
| **SharpDX.Color.Violet** | Violet color |
| **SharpDX.Color.Wheat** | Wheat color |
| **SharpDX.Color.White** | White color |
| **SharpDX.Color.WhiteSmoke** | WhiteSmoke color |
| **SharpDX.Color.Yellow** | Yellow color |
| **SharpDX.Color.YellowGreen** | YellowGreen color |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#definition)

Represents a 32-bit color (4 bytes) in the form of RGBA (in byte order: R, G, B, A).

## Note

Notes:

1. The color of each pixel is represented as a 32-bit number: 8 bits each for alpha, red, green, and blue (ARGB). Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity. The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque. To determine the alpha, red, green, or blue component of a color, use the **A**, **R**, **G**, or **B** property, respectively.
2. Named colors are represented by using the properties of the Color structure. Please see the table of Static Named Colors below.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#syntax)

`struct Color`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#constructors)

| Constructor | Description |
| --- | --- |
| `new Color()` | Initializes a new instance of the `Color` struct |
| `new Color(float red, float green, float blue)` | Initializes a new instance of the **Color** struct using float values |
| new `Color(float red, float green, float blue, float alpha)` Inializes a new instance of the **Color** struct using float values with alpha transparency |
| `new Color(int red, int green, int blue)` | Initializes a new instance of the **Color** struct using int values |
| `new Color(int red, int green, int blue, int alpha)` | Initializes a new instance of the **Color** struct using int values with alpha transparency |
| `new Color(byte red, byte green, byte blue)` | Initializes a new instance of the **Color** struct using byte values |
| `new Color(byte red, byte green, byte blue, byte alpha)` | Initializes a new instance of the **Color** struct using byte values with alpha transparency |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| **R** | The red component of the color |
| **G** | The green component of the color |
| **B** | The blue component of the color |
| **A** | The alpha component of the color |
| **ToColor3()** | Converts the color into a [three component](https://developer.ninjatrader.com/docs/desktop/sharpdx_color3) color |
| **ToColor4()** | Converts the color into a [four component](https://developer.ninjatrader.com/docs/desktop/sharpdx_color4) color |

## [Static Named Colors](https://developer.ninjatrader.com/docs/desktop/sharpdx_color\#static-named-colors)

### Colors by name

| Color Name | Description |
| --- | --- |
| **SharpDX.Color.Zero** | Zero color |
| **SharpDX.Color.Transparent** | Transparent color |
| **SharpDX.Color.AliceBlue** | AliceBlue color |
| **SharpDX.Color.AntiqueWhite** | AntiqueWhite color |
| **SharpDX.Color.Aqua** | Aqua color |
| **SharpDX.Color.Aquamarine** | Aquamarine color |
| **SharpDX.Color.Azure** | Azure color |
| **SharpDX.Color.Beige** | Beige color |
| **SharpDX.Color.Bisque** | Bisque color |
| **SharpDX.Color.Black** | Black color |
| **SharpDX.Color.BlanchedAlmond** | BlanchedAlmond color |
| **SharpDX.Color.Blue** | Blue color |
| **SharpDX.Color.BlueViolet** | BlueViolet color |
| **SharpDX.Color.Brown** | Brown color |
| **SharpDX.Color.BurlyWood** | BurlyWood color |
| **SharpDX.Color.CadetBlue** | CadetBlue color |
| **SharpDX.Color.Chartreuse** | Chartreuse color |
| **SharpDX.Color.Chocolate** | Chocolate color |
| **SharpDX.Color.Coral** | Coral color |
| **SharpDX.Color.CornflowerBlue** | CornflowerBlue color |
| **SharpDX.Color.Cornsilk** | Cornsilk color |
| **SharpDX.Color.Crimson** | Crimson color |
| **SharpDX.Color.Cyan** | Cyan color |
| **SharpDX.Color.DarkBlue** | DarkBlue color |
| **SharpDX.Color.DarkCyan** | DarkCyan color |
| **SharpDX.Color.DarkGoldenrod** | DarkGoldenrod color |
| **SharpDX.Color.DarkGray** | DarkGray color |
| **SharpDX.Color.DarkGreen** | DarkGreen color |
| **SharpDX.Color.DarkKhaki** | DarkKhaki color |
| **SharpDX.Color.DarkMagenta** | DarkMagenta color |
| **SharpDX.Color.DarkOliveGreen** | DarkOliveGreen color |
| **SharpDX.Color.DarkOrange** | DarkOrange color |
| **SharpDX.Color.DarkOrchid** | DarkOrchid color |
| **SharpDX.Color.DarkRed** | DarkRed color |
| **SharpDX.Color.DarkSalmon** | DarkSalmon color |
| **SharpDX.Color.DarkSeaGreen** | DarkSeaGreen color |
| **SharpDX.Color.DarkSlateBlue** | DarkSlateBlue color |
| **SharpDX.Color.DarkSlateGray** | DarkSlateGray color |
| **SharpDX.Color.DarkTurquoise** | DarkTurquoise color |
| **SharpDX.Color.DarkViolet** | DarkViolet color |
| **SharpDX.Color.DeepPink** | DeepPink color |
| **SharpDX.Color.DeepSkyBlue** | DeepSkyBlue color |
| **SharpDX.Color.DimGray** | DimGray color |
| **SharpDX.Color.DodgerBlue** | DodgerBlue color |
| **SharpDX.Color.Firebrick** | Firebrick color |
| **SharpDX.Color.FloralWhite** | FloralWhite color |
| **SharpDX.Color.ForestGreen** | ForestGreen color |
| **SharpDX.Color.Fuchsia** | Fuchsia color |
| **SharpDX.Color.Gainsboro** | Gainsboro color |
| **SharpDX.Color.GhostWhite** | GhostWhite color |
| **SharpDX.Color.Gold** | Gold color |
| **SharpDX.Color.Goldenrod** | Goldenrod color |
| **SharpDX.Color.Gray** | Gray color |
| **SharpDX.Color.Green** | Green color |
| **SharpDX.Color.GreenYellow** | GreenYellow color |
| **SharpDX.Color.Honeydew** | Honeydew color |
| **SharpDX.Color.HotPink** | HotPink color |
| **SharpDX.Color.IndianRed** | IndianRed color |
| **SharpDX.Color.Indigo** | Indigo color |
| **SharpDX.Color.Ivory** | Ivory color |
| **SharpDX.Color.Khaki** | Khaki color |
| **SharpDX.Color.Lavender** | Lavender color |
| **SharpDX.Color.LavenderBlush** | LavenderBlush color |
| **SharpDX.Color.LawnGreen** | LawnGreen color |
| **LemonChiffon** | LemonChiffon color |
| **SharpDX.Color.LightBlue** | LightBlue color |
| **SharpDX.Color.LightCoral** | LightCoral color |
| **SharpDX.Color.LightCyan** | LightCyan color |
| **SharpDX.Color.LightGoldenrodYellow** | LightGoldenrodYellow color |
| **SharpDX.Color.LightGray** | LightGray color |
| **SharpDX.Color.LightGreen** | LightGreen color |
| **SharpDX.Color.LightPink** | LightPink color |
| **SharpDX.Color.LightSalmon** | LightSalmon color |
| **SharpDX.Color.LightSeaGreen** | LightSeaGreen color |
| **SharpDX.Color.LightSkyBlue** | LightSkyBlue color |
| **SharpDX.Color.LightSlateGray** | LightSlateGray color |
| **SharpDX.Color.LightSteelBlue** | LightSteelBlue color |
| **SharpDX.Color.LightYellow** | LightYellow color |
| **SharpDX.Color.Lime** | Lime color |
| **SharpDX.Color.LimeGreen** | LimeGreen color |
| **SharpDX.Color.Linen** | Linen color |
| **SharpDX.Color.Magenta** | Magenta color |
| **SharpDX.Color.Maroon** | Maroon color |
| **SharpDX.Color.MediumAquamarine** | MediumAquamarine color |
| **SharpDX.Color.MediumBlue** | MediumBlue color |
| **SharpDX.Color.MediumOrchid** | MediumOrchid color |
| **SharpDX.Color.MediumPurple** | MediumPurple color |
| **SharpDX.Color.MediumSeaGreen** | MediumSeaGreen color |
| **SharpDX.Color.MediumSlateBlue** | MediumSlateBlue color |
| **SharpDX.Color.MediumSpringGreen** | MediumSpringGreen color |
| **SharpDX.Color.MediumTurquoise** | MediumTurquoise color |
| **SharpDX.Color.MediumVioletRed** | MediumVioletRed color |
| **SharpDX.Color.MidnightBlue** | MidnightBlue color |
| **SharpDX.Color.MintCream** | MintCream color |
| **SharpDX.Color.MistyRose** | MistyRose color |
| **SharpDX.Color.Moccasin** | Moccasin color |
| **SharpDX.Color.NavajoWhite** | NavajoWhite color |
| **SharpDX.Color.Navy** | Navy color |
| **SharpDX.Color.OldLace** | OldLace color |
| **SharpDX.Color.Olive** | Olive color |
| **SharpDX.Color.OliveDrab** | OliveDrab color |
| **SharpDX.Color.Orange** | Orange color |
| **SharpDX.Color.OrangeRed** | OrangeRed color |
| **SharpDX.Color.Orchid** | Orchid color |
| **SharpDX.Color.PaleGoldenrod** | PaleGoldenrod color |
| **SharpDX.Color.PaleGreen** | PaleGreen color |
| **SharpDX.Color.PaleTurquoise** | PaleTurquoise color |
| **SharpDX.Color.PaleVioletRed** | PaleVioletRed color |
| **SharpDX.Color.PapayaWhip** | PapayaWhip color |
| **SharpDX.Color.PeachPuff** | PeachPuff color |
| **SharpDX.Color.Peru** | Peru color |
| **SharpDX.Color.Pink** | Pink color |
| **SharpDX.Color.Plum** | Plum color |
| **SharpDX.Color.PowderBlue** | PowderBlue color |
| **SharpDX.Color.Purple** | Purple color |
| **SharpDX.Color.Red** | Red color |
| **SharpDX.Color.RosyBrown** | RosyBrown color |
| **SharpDX.Color.RoyalBlue** | RoyalBlue color |
| **SharpDX.Color.SaddleBrown** | SaddleBrown color |
| **SharpDX.Color.Salmon** | Salmon color |
| **SharpDX.Color.SandyBrown** | SandyBrown color |
| **SharpDX.Color.SeaGreen** | SeaGreen color |
| **SharpDX.Color.SeaShell** | SeaShell color |
| **SharpDX.Color.Sienna** | Sienna color |
| **SharpDX.Color.Silver** | Silver color |
| **SharpDX.Color.SkyBlue** | SkyBlue color |
| **SharpDX.Color.SlateBlue** | SlateBlue color |
| **SharpDX.Color.SlateGray** | SlateGray color |
| **SharpDX.Color.Snow** | Snow color |
| **SharpDX.Color.SpringGreen** | SpringGreen color |
| **SharpDX.Color.SteelBlue** | SteelBlue color |
| **SharpDX.Color.Tan** | Tan color |
| **SharpDX.Color.Teal** | Teal color |
| **SharpDX.Color.Thistle** | Thistle color |
| **SharpDX.Color.Tomato** | Tomato color |
| **SharpDX.Color.Turquoise** | Turquoise color |
| **SharpDX.Color.Violet** | Violet color |
| **SharpDX.Color.Wheat** | Wheat color |
| **SharpDX.Color.White** | White color |
| **SharpDX.Color.WhiteSmoke** | WhiteSmoke color |
| **SharpDX.Color.Yellow** | Yellow color |
| **SharpDX.Color.YellowGreen** | YellowGreen color |