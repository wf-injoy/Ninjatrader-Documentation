## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#definition)

Represents a 3x2 mathematical matrix.

## Note

Tip: For more information on Direct2D transforms, please see the [MSDN Direct2D Transforms Overview](https://msdn.microsoft.com/en-us/library/dd756655(v=vs.85).aspx).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#syntax)

`struct Matrix3x2`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#constructors)

| Constructor | Description |
| --- | --- |
| **new Matrix3x2()** | Initializes a new instance of the Matrix3x2 struct |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| **Identity** | Gets the identity matrix. |
| **M11** | A float for the first element of the first row. |
| **M12** | A float for the second element of the first row. |
| **M21** | A float for the first element of the second row. |
| **M22** | A float for the second element of the second row. |
| **M31** | A float for the first element of the third row. |
| **M32** | A float for the second element of the third row. |
| **TranslationVector** | A [SharpDX.Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) for the translation component of this matrix. |
| **Matrix3x2.Rotation(float angle)** | Creates a matrix that rotates. |
| **Matrix3x2.Scaling(float scale)** | Creates a matrix that uniformally scales along all three axis. |
| **Translation( [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) value)** | Creates a translation matrix using the specified offsets. |

## Warning

Disclaimer: The **SharpDX SDK Reference** section was compiled from the official **SharpDX Documentation** and was NOT authored by NinjaTrader. The contents of this section are provided as-is and only cover a fraction of what is available from the SharpDX SDK. This page was intended only as a reference guide to help you get started with some of the 2D Graphics concepts used in the NinjaTrader.Custom assembly. Please refer to the official SharpDX Documentation for additional members not covered in this reference. For more seasoned graphic developers, the original MSDN **Direct2D1** and **DirectWrite** unmanaged API documentation can also be helpful for understanding the DirectX/Direct2D run-time environment. For NinjaScript development purposes, we document only essential members in the structure of this page.

## [Definition](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#definition)

Represents a 3x2 mathematical matrix.

## Note

Tip: For more information on Direct2D transforms, please see the [MSDN Direct2D Transforms Overview](https://msdn.microsoft.com/en-us/library/dd756655(v=vs.85).aspx).

## [Syntax](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#syntax)

`struct Matrix3x2`

## [Constructors](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#constructors)

| Constructor | Description |
| --- | --- |
| **new Matrix3x2()** | Initializes a new instance of the Matrix3x2 struct |

## [Methods and Properties](https://developer.ninjatrader.com/docs/desktop/sharpdx_matrix3x2\#methods-and-properties)

| Property/Method | Description |
| --- | --- |
| **Identity** | Gets the identity matrix. |
| **M11** | A float for the first element of the first row. |
| **M12** | A float for the second element of the first row. |
| **M21** | A float for the first element of the second row. |
| **M22** | A float for the second element of the second row. |
| **M31** | A float for the first element of the third row. |
| **M32** | A float for the second element of the third row. |
| **TranslationVector** | A [SharpDX.Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) for the translation component of this matrix. |
| **Matrix3x2.Rotation(float angle)** | Creates a matrix that rotates. |
| **Matrix3x2.Scaling(float scale)** | Creates a matrix that uniformally scales along all three axis. |
| **Translation( [Vector2](https://developer.ninjatrader.com/docs/desktop/sharpdx_vector2) value)** | Creates a translation matrix using the specified offsets. |