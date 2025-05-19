In order to achieve custom rendering for various chart related objects, a Brush is used to "paint" an area or another chart object.  There are a number of different brushes which are available through the .NET Framework, where the most common type of brush is a [SolidColorBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.solidcolorbrush(v=vs.110).aspx) which is used to paint an area with a single solid color.

## Note

The following document is written in sequential fashion, starting with the most simple concepts, to the more advance topics.  The majority of the brushes discussed in this document will be referred to as "WPF" brushes which exist in the System.Windows.Media namespace, however there are also "SharpDX" brushes which exist in the 3rd party SharpDX.Direct2D1 namespace used for advanced chart rendering.  Advanced brush types should ONLY be used by experienced programmers familiar with .NET graphics functionality.

## [Understanding predefined brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#understanding-predefined-brushes)

### Using Predefined Brushes

For convenience, the .NET Framework supplies a collection of static predefined Brushes, such as Red or Green.  The advantage to using these brushes is that they are readily available, properly named to quickly find a simple color value, and can be reused on-the-fly without having to recreate an instance of the brush at run time, and do not need to be otherwise managed.  There are 256 predefined named brushes which are available in the Brushes class.  You can browse this list in the NinjaScript editor just by typing Brushes. and using Intelliprompt to find the desired named brush of your choice.

## Note

Since predefined brushes are static, properties of the brush object (such as Color, Opacity, etc.) CANNOT be modified.  However, this also means predefined brushes are thread-safe and do NOT need to be frozen.  For customizing and freezing a brush, please see the section below on Creating a Custom Solid Color Brush.\|

## Note

Tip:  You can also find a list of these predefined brushes as well as their hexadecimal value on the MSDN article for the [Brushes Class](https://msdn.microsoft.com/en-us/library/system.windows.media.brushes(v=vs.110).aspx) \|

```jsx-150469391 csharp
// set the chart's background color to a predefined "Blue" brush
BackBrush = Brushes.Blue;

//draw a line using a predefined "LimeGreen" brush.
Draw.Line(this, "tag1", false, 10, 1000, 0, 1001, Brushes.LimeGreen, DashStyleHelper.Dot, 2);|   |

```

## [Understanding custom brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#understanding-custom-brushes)

### Creating a Custom Solid Color Brush

In cases where you would like more specific color than one of the predefined brushes, you can optionally create your own Brush object to be used for custom rendering.  In order to achieve this, you will need to initiate your own custom brush object, where you can then specify your color using RGB (red, green, blue) values [Color.FromRgb()](https://msdn.microsoft.com/en-us/library/system.windows.media.color.fromrgb(v=vs.110).aspx).

## Note

- Anytime you create a custom brush that will be used by NinjaTrader rendering it must be frozen using the . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx)  method due to the multi-threaded nature of NinjaTrader.

- You may have up to 65535 unique Brush instances, therefore, using static predefined brushes (as in the section above) should be favored.  Alternatively,  in order to use fewer brushes, please try to cache your custom brushes until a new brush would actually need to be created.\|


```jsx-150469391 csharp
// initiate new solid color brush with custom blue color
Brush myBrush = new SolidColorBrush(Color.FromRgb(56, 120, 153));
myBrush.Freeze();

Draw.Line(this, "tag1", true, 10, 1000, 0, 1001, myBrush, DashStyleHelper.Dot, 2);

```

## Warning

If you do not call . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx) on a custom defined brush WILL eventually result in threading errors should you try to modify or access that brush after it is defined.

### Creating a Transparent Solid Color Brush

You can create a transparent brush using the [Color.FromArgb()](https://msdn.microsoft.com/en-us/library/system.windows.media.color.fromargb(v=vs.110).aspx) where the A parameter defines alpha transparency.

## Note

Anytime you create a custom brush that will be used by NinjaTrader rendering it must be frozen using the . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx)  method due to the multi-threaded nature of NinjaTrader.

```jsx-150469391 csharp
// initiate new solid color brush which has an alpha (transparency) value of 100
myBrush = new SolidColorBrush(Color.FromArgb(100, 56, 120, 153));
myBrush.Freeze();

Draw.Line(this, "tag1", true, 10, 1000, 0, 1001, myBrush, DashStyleHelper.Dot, 2);

```

## Warning

If you do not call . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx) on a custom defined brush WILL eventually result in threading errors should you try to modify or access that brush after it is defined.

## [Using brushes defined on the user interface](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#using-brushes-defined-on-the-user-interface)

### Saving a Brush as a user defined property (Serialization)

If you would like a brush to become a public UI property, meaning the brush can be set up and defined by a user during configuration, it is important to be able to save the user's brush selection in order to restore that brush either from a workspace or from a template file at a later time.  Saving a custom defined user input is done through a concept of [Serialization](https://msdn.microsoft.com/en-us/library/ms233843.aspx) which writes the object and its value to a .xml file.  This process normally works fine for a simple user defined value type (such as a double or an int) but for more complex types such as Brushes, the object itself cannot be serialized directly to the .xml file and will result in errors upon saving the indicator or strategy to a workspace or template file.  The example below will demonstrate and explain how to properly store a user define brush input which will be correctly serialized.

In order to achieve the desired behavior of saving the user defined brush input, we will add the [XmlIgnore](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlignoreattribute(v=vs.110).aspx) property attribute to the public brush resource, which essentially tells the serialization routine to ignore this property.

```jsx-150469391 csharp
[XmlIgnore]
public Brush MyBrush { get; set; }

```

In its place, we create a new public string called "MyBrushSerialize" which will convert the public "MyBrush" to a string type which can then be processed by the serialization routines.  We also add the [Browsable(false)](https://msdn.microsoft.com/en-us/library/system.componentmodel.browsableattribute(v=vs.110).aspx) attribute to this public string to prevent this property from showing up on the UI, which is of no value to the end user.

```jsx-150469391 csharp
[Browsable(false)]
public string MyBrushSerialize
{
  get { return Serialize.BrushToString(MyBrush); }
  set { MyBrush = Serialize.StringToBrush(value); }
}

```

## Note

Tip: For a complete example of User Definable Color Inputs, please see the reference sample [here](https://developer.ninjatrader.com/docs/desktop/user_definable_color_inputs).

### Adding a User Defined Brush to the Color Picker

You can optionally define a custom brush to be added to the standard color picker by using a \[CustomBrush\] attribute to a public brush.  The CustomBrush attribute will then add it to the color picker menu for that indicator when you look through the plots, lines, or other brushes from the indicators configured menu and will be listed toward the top of the list (as pictured below)

```jsx-150469391 csharp
[CustomBrush]
public Brush MyBrush
{
  get { return new SolidColorBrush(Color.FromRgb(25, 175, 185)); }
  set { }
}

```

## [Using advanced brush types (SharpDX)](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#using-advanced-brush-types-(sharpdx))

### Understanding SharpDX Brushes

While the majority of the NinjaTrader platform's UI is WPF, under the hood, chart's use a DirectX API for faster performance.  To render custom objects to a chart during [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender), a particular SharpDX Brush object must be implemented which reside in the SharpDX.Direct2D1 namespace.   These brushes can then be passed as arguments to the SharpDX [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) methods such [FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle), [DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline), etc.  While SharpDX Brushes behave much the same as previously discussed WPF Brushes, there are a few special considerations you must take as detailed in the following sections.

## Note

The SharpDX Brushes used in [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) methods should NOT be confused with the WPF Brushes used with [DrawingTool Draw](https://developer.ninjatrader.com/docs/desktop/drawing) methods.

### Creating a SharpDX Brush

A [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) must be created either in OnRender() or RenderTargetChanged().  If you have custom brushes which may be changed on various conditions such as in OnBarUpdate() or by a user during OnStateChange(), or you are pre-computing a custom brush for performance optimization, you will need to ensure the actual SharpDX instance is updated in OnRender() or RenderTargetChange().

## Warning

Each DirectX render target requires its own brushes. You MUST create brushes directly in OnRender() or using OnRenderTargetChanged().  If you do not you will receive an error at runtime similar to:

> "A direct X error has occured while rendering the chart: HRESULT: \[0x88990015\], Module: \[SharpDX.Direct2D1\], ApiCode: \[D2DERR\_WRONG\_RESOURCE\_DOMAIN/WrongResourceDomain\], Message: The resource was realized on the wrong render target. : Each DirectX render target requires its own brushes. You must create brushes directly in OnRender() or using OnRenderTargetChanged().

Please see [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) for examples of a brush that needs to be recalculated, or [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) for an example of recreating a static brush.

```jsx-150469391 csharp
// use predefined "Blue" SharpDX Color
SharpDX.Direct2D1.SolidColorBrush solidBlueDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue);

// create custom Brush using a "Red" SharpDX Color with "Alpha" (0.100f) transparency/opacity
SharpDX.Direct2D1.SolidColorBrush transparentRedDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, new SharpDX.Color4(new SharpDX.Color3(220f, 0f, 0f), 0.100f));|

```

### Converting to SharpDX Brush

For convenience, you can convert a computed WPF Brush to a [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) using the [ToDxBrush(](https://developer.ninjatrader.com/docs/desktop/todxbrush)) extension method.

## Warning

Converting ToDxBrush() can result in performance issues depending on the number of brushes being used. If you experience performance issues with your custom SharpDX rendering, you should favor using SharpDX brushes directly instead of converting the brush using ToDxBrush().

```jsx-150469391 csharp
// convert predefined WPF "Blue" to SharpDX Brush
SharpDX.Direct2D1.Brush blueDXBrush = Brushes.Blue.ToDxBrush(RenderTarget);

// convert the computed WPF Brush to SharpDX Brush
SharpDX.Direct2D1.Brush customDXBrush = customWPFBrush.ToDxBrush(RenderTarget);|

```

### Disposing DXBrush

Since SharpDX Brushes reference unmanaged resources, these brushes should always be [disposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase) of after they have been used.

## Warning

Failing to dispose of a [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) and other unmanaged resources can cause the platform to utilize more memory than necessary.

```jsx-1168641291 csharp
customDXBrush.Dipose();

```

### Using Complex Brushes

In addition to the [SolidColorBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.solidcolorbrush(v=vs.110).aspx) object demonstrated on this page, the .NET Framework provides more complex brushes which have more attributes than just filling an area with a solid color.  Information on these special types of brushes can be found on the MSDN website: [LinearGradientBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.lineargradientbrush(v=vs.110).aspx), [RadialGradientBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.radialgradientbrush(v=vs.110).aspx), [ImageBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.imagebrush(v=vs.110).aspx).

These complex types also have an equivalent found in the SharpDX SDK Reference: [SharpDX.Direct2D1.LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush), [SharpDX.Direct2D1.RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)

In order to achieve custom rendering for various chart related objects, a Brush is used to "paint" an area or another chart object.  There are a number of different brushes which are available through the .NET Framework, where the most common type of brush is a [SolidColorBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.solidcolorbrush(v=vs.110).aspx) which is used to paint an area with a single solid color.

## Note

The following document is written in sequential fashion, starting with the most simple concepts, to the more advance topics.  The majority of the brushes discussed in this document will be referred to as "WPF" brushes which exist in the System.Windows.Media namespace, however there are also "SharpDX" brushes which exist in the 3rd party SharpDX.Direct2D1 namespace used for advanced chart rendering.  Advanced brush types should ONLY be used by experienced programmers familiar with .NET graphics functionality.

## [Understanding predefined brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#understanding-predefined-brushes)

### Using Predefined Brushes

For convenience, the .NET Framework supplies a collection of static predefined Brushes, such as Red or Green.  The advantage to using these brushes is that they are readily available, properly named to quickly find a simple color value, and can be reused on-the-fly without having to recreate an instance of the brush at run time, and do not need to be otherwise managed.  There are 256 predefined named brushes which are available in the Brushes class.  You can browse this list in the NinjaScript editor just by typing Brushes. and using Intelliprompt to find the desired named brush of your choice.

## Note

Since predefined brushes are static, properties of the brush object (such as Color, Opacity, etc.) CANNOT be modified.  However, this also means predefined brushes are thread-safe and do NOT need to be frozen.  For customizing and freezing a brush, please see the section below on Creating a Custom Solid Color Brush.\|

## Note

Tip:  You can also find a list of these predefined brushes as well as their hexadecimal value on the MSDN article for the [Brushes Class](https://msdn.microsoft.com/en-us/library/system.windows.media.brushes(v=vs.110).aspx) \|

```jsx-150469391 csharp
// set the chart's background color to a predefined "Blue" brush
BackBrush = Brushes.Blue;

//draw a line using a predefined "LimeGreen" brush.
Draw.Line(this, "tag1", false, 10, 1000, 0, 1001, Brushes.LimeGreen, DashStyleHelper.Dot, 2);|   |

```

## [Understanding custom brushes](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#understanding-custom-brushes)

### Creating a Custom Solid Color Brush

In cases where you would like more specific color than one of the predefined brushes, you can optionally create your own Brush object to be used for custom rendering.  In order to achieve this, you will need to initiate your own custom brush object, where you can then specify your color using RGB (red, green, blue) values [Color.FromRgb()](https://msdn.microsoft.com/en-us/library/system.windows.media.color.fromrgb(v=vs.110).aspx).

## Note

- Anytime you create a custom brush that will be used by NinjaTrader rendering it must be frozen using the . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx)  method due to the multi-threaded nature of NinjaTrader.

- You may have up to 65535 unique Brush instances, therefore, using static predefined brushes (as in the section above) should be favored.  Alternatively,  in order to use fewer brushes, please try to cache your custom brushes until a new brush would actually need to be created.\|


```jsx-150469391 csharp
// initiate new solid color brush with custom blue color
Brush myBrush = new SolidColorBrush(Color.FromRgb(56, 120, 153));
myBrush.Freeze();

Draw.Line(this, "tag1", true, 10, 1000, 0, 1001, myBrush, DashStyleHelper.Dot, 2);

```

## Warning

If you do not call . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx) on a custom defined brush WILL eventually result in threading errors should you try to modify or access that brush after it is defined.

### Creating a Transparent Solid Color Brush

You can create a transparent brush using the [Color.FromArgb()](https://msdn.microsoft.com/en-us/library/system.windows.media.color.fromargb(v=vs.110).aspx) where the A parameter defines alpha transparency.

## Note

Anytime you create a custom brush that will be used by NinjaTrader rendering it must be frozen using the . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx)  method due to the multi-threaded nature of NinjaTrader.

```jsx-150469391 csharp
// initiate new solid color brush which has an alpha (transparency) value of 100
myBrush = new SolidColorBrush(Color.FromArgb(100, 56, 120, 153));
myBrush.Freeze();

Draw.Line(this, "tag1", true, 10, 1000, 0, 1001, myBrush, DashStyleHelper.Dot, 2);

```

## Warning

If you do not call . [Freeze()](https://msdn.microsoft.com/en-us/library/ms557735(v=vs.110).aspx) on a custom defined brush WILL eventually result in threading errors should you try to modify or access that brush after it is defined.

## [Using brushes defined on the user interface](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#using-brushes-defined-on-the-user-interface)

### Saving a Brush as a user defined property (Serialization)

If you would like a brush to become a public UI property, meaning the brush can be set up and defined by a user during configuration, it is important to be able to save the user's brush selection in order to restore that brush either from a workspace or from a template file at a later time.  Saving a custom defined user input is done through a concept of [Serialization](https://msdn.microsoft.com/en-us/library/ms233843.aspx) which writes the object and its value to a .xml file.  This process normally works fine for a simple user defined value type (such as a double or an int) but for more complex types such as Brushes, the object itself cannot be serialized directly to the .xml file and will result in errors upon saving the indicator or strategy to a workspace or template file.  The example below will demonstrate and explain how to properly store a user define brush input which will be correctly serialized.

In order to achieve the desired behavior of saving the user defined brush input, we will add the [XmlIgnore](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlignoreattribute(v=vs.110).aspx) property attribute to the public brush resource, which essentially tells the serialization routine to ignore this property.

```jsx-150469391 csharp
[XmlIgnore]
public Brush MyBrush { get; set; }

```

In its place, we create a new public string called "MyBrushSerialize" which will convert the public "MyBrush" to a string type which can then be processed by the serialization routines.  We also add the [Browsable(false)](https://msdn.microsoft.com/en-us/library/system.componentmodel.browsableattribute(v=vs.110).aspx) attribute to this public string to prevent this property from showing up on the UI, which is of no value to the end user.

```jsx-150469391 csharp
[Browsable(false)]
public string MyBrushSerialize
{
  get { return Serialize.BrushToString(MyBrush); }
  set { MyBrush = Serialize.StringToBrush(value); }
}

```

## Note

Tip: For a complete example of User Definable Color Inputs, please see the reference sample [here](https://developer.ninjatrader.com/docs/desktop/user_definable_color_inputs).

### Adding a User Defined Brush to the Color Picker

You can optionally define a custom brush to be added to the standard color picker by using a \[CustomBrush\] attribute to a public brush.  The CustomBrush attribute will then add it to the color picker menu for that indicator when you look through the plots, lines, or other brushes from the indicators configured menu and will be listed toward the top of the list (as pictured below)

```jsx-150469391 csharp
[CustomBrush]
public Brush MyBrush
{
  get { return new SolidColorBrush(Color.FromRgb(25, 175, 185)); }
  set { }
}

```

## [Using advanced brush types (SharpDX)](https://developer.ninjatrader.com/docs/desktop/working_with_brushes\#using-advanced-brush-types-(sharpdx))

### Understanding SharpDX Brushes

While the majority of the NinjaTrader platform's UI is WPF, under the hood, chart's use a DirectX API for faster performance.  To render custom objects to a chart during [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender), a particular SharpDX Brush object must be implemented which reside in the SharpDX.Direct2D1 namespace.   These brushes can then be passed as arguments to the SharpDX [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) methods such [FillRectangle()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_fillrectangle), [DrawLine()](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_rendertarget_drawline), etc.  While SharpDX Brushes behave much the same as previously discussed WPF Brushes, there are a few special considerations you must take as detailed in the following sections.

## Note

The SharpDX Brushes used in [RenderTarget](https://developer.ninjatrader.com/docs/desktop/rendertarget) methods should NOT be confused with the WPF Brushes used with [DrawingTool Draw](https://developer.ninjatrader.com/docs/desktop/drawing) methods.

### Creating a SharpDX Brush

A [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) must be created either in OnRender() or RenderTargetChanged().  If you have custom brushes which may be changed on various conditions such as in OnBarUpdate() or by a user during OnStateChange(), or you are pre-computing a custom brush for performance optimization, you will need to ensure the actual SharpDX instance is updated in OnRender() or RenderTargetChange().

## Warning

Each DirectX render target requires its own brushes. You MUST create brushes directly in OnRender() or using OnRenderTargetChanged().  If you do not you will receive an error at runtime similar to:

> "A direct X error has occured while rendering the chart: HRESULT: \[0x88990015\], Module: \[SharpDX.Direct2D1\], ApiCode: \[D2DERR\_WRONG\_RESOURCE\_DOMAIN/WrongResourceDomain\], Message: The resource was realized on the wrong render target. : Each DirectX render target requires its own brushes. You must create brushes directly in OnRender() or using OnRenderTargetChanged().

Please see [OnRenderTargetChanged()](https://developer.ninjatrader.com/docs/desktop/onrendertargetchanged) for examples of a brush that needs to be recalculated, or [OnRender()](https://developer.ninjatrader.com/docs/desktop/onrender) for an example of recreating a static brush.

```jsx-150469391 csharp
// use predefined "Blue" SharpDX Color
SharpDX.Direct2D1.SolidColorBrush solidBlueDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, SharpDX.Color.Blue);

// create custom Brush using a "Red" SharpDX Color with "Alpha" (0.100f) transparency/opacity
SharpDX.Direct2D1.SolidColorBrush transparentRedDXBrush = new SharpDX.Direct2D1.SolidColorBrush(RenderTarget, new SharpDX.Color4(new SharpDX.Color3(220f, 0f, 0f), 0.100f));|

```

### Converting to SharpDX Brush

For convenience, you can convert a computed WPF Brush to a [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) using the [ToDxBrush(](https://developer.ninjatrader.com/docs/desktop/todxbrush)) extension method.

## Warning

Converting ToDxBrush() can result in performance issues depending on the number of brushes being used. If you experience performance issues with your custom SharpDX rendering, you should favor using SharpDX brushes directly instead of converting the brush using ToDxBrush().

```jsx-150469391 csharp
// convert predefined WPF "Blue" to SharpDX Brush
SharpDX.Direct2D1.Brush blueDXBrush = Brushes.Blue.ToDxBrush(RenderTarget);

// convert the computed WPF Brush to SharpDX Brush
SharpDX.Direct2D1.Brush customDXBrush = customWPFBrush.ToDxBrush(RenderTarget);|

```

### Disposing DXBrush

Since SharpDX Brushes reference unmanaged resources, these brushes should always be [disposed](https://developer.ninjatrader.com/docs/desktop/sharpdx_disposebase) of after they have been used.

## Warning

Failing to dispose of a [SharpDX Brush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_brush) and other unmanaged resources can cause the platform to utilize more memory than necessary.

```jsx-1168641291 csharp
customDXBrush.Dipose();

```

### Using Complex Brushes

In addition to the [SolidColorBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.solidcolorbrush(v=vs.110).aspx) object demonstrated on this page, the .NET Framework provides more complex brushes which have more attributes than just filling an area with a solid color.  Information on these special types of brushes can be found on the MSDN website: [LinearGradientBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.lineargradientbrush(v=vs.110).aspx), [RadialGradientBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.radialgradientbrush(v=vs.110).aspx), [ImageBrush](https://msdn.microsoft.com/en-us/library/system.windows.media.imagebrush(v=vs.110).aspx).

These complex types also have an equivalent found in the SharpDX SDK Reference: [SharpDX.Direct2D1.LinearGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_lineargradientbrush), [SharpDX.Direct2D1.RadialGradientBrush](https://developer.ninjatrader.com/docs/desktop/sharpdx_direct2d1_radialgradientbrush)