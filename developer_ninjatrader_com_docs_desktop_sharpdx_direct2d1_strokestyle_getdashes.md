## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#definition)

Copies the dash pattern to the specified array.

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd372230.aspx))

## Note

The dashes are specified in units that are a multiple of the stroke width, with subsequent members of the array indicating the dashes and gaps between dashes: the first entry indicates a filled dash, the second a gap, and so on.

## [Method return value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#syntax)

`<strokestyle>.GetDashes(float[] dashes, int dashesCount)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#parameters)

| dashes | A float pointer to an array that will receive the dash pattern. The array must be able to contain at least as many elements as specified by dashesCount. You must allocate storage for this array. |
| dashesCount | The int number of dashes to copy. If this value is less than the number of dashes in the stroke style's dashes array, the returned dashes are truncated to dashesCount. If this value is greater than the number of dashes in the stroke style's dashes array, the extra dashes are set to 0.0f. To obtain the actual number of dashes in the stroke style's dashes array, use the **DashesCount** property. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#definition)

Copies the dash pattern to the specified array.

(See also [unmanaged API documentation](https://msdn.microsoft.com/en-us/library/dd372230.aspx))

## Note

The dashes are specified in units that are a multiple of the stroke width, with subsequent members of the array indicating the dashes and gaps between dashes: the first entry indicates a filled dash, the second a gap, and so on.

## [Method return value](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#syntax)

`<strokestyle>.GetDashes(float[] dashes, int dashesCount)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_strokestyle_getdashes\#parameters)

| dashes | A float pointer to an array that will receive the dash pattern. The array must be able to contain at least as many elements as specified by dashesCount. You must allocate storage for this array. |
| dashesCount | The int number of dashes to copy. If this value is less than the number of dashes in the stroke style's dashes array, the returned dashes are truncated to dashesCount. If this value is greater than the number of dashes in the stroke style's dashes array, the extra dashes are set to 0.0f. To obtain the actual number of dashes in the stroke style's dashes array, use the **DashesCount** property. |