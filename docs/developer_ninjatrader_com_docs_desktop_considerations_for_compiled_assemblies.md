## [Using Compiled Assemblies](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#using-compiled-assemblies)

Compiled assemblies (DLL's) allow you to bundle your scripts into a format that hides your proprietary code along with any supporting resources. Compiled assemblies provide distinct benefits, especially for commercially distributed code, but there are a few considerations to keep in mind. Typecasting and building resource files (sounds, images, etc.) into your assemblies must be approached differently to ensure cleanly packaged, error-free DLL's.

## [Using Custom enum Properties](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#using-custom-enum-properties)

When creating custom enum properties, it is advised to create the enum outside of your **NinjaScript** class, and designating it in its own fully qualified namespace. For an example, please see [here](https://developer.ninjatrader.com/docs/desktop/creating_a_user_defined_parameter_type_enum). When using the enum in code, please use the fully qualified namespace as opposed to using a using directive to shorthand the expression.

## [Casting Types in a DLL (Using dynamic Types)](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#casting-types-in-a-dll-(using-dynamic-types))

Sometimes, you may need to cast your objects to **NinjaScript** types, such as when iterating through the **DrawObjects** collection to obtain a reference to a particular Drawing Object on a chart. When running **C#** code which has not been compiled into an assembly, typecasting can be done normally, as in the example below:

```jsx-150469391 csharp
// Typecasting in code outside of a compiled assembly

protected override void OnBarUpdate()
{
   foreach(HorizontalLine line in DrawObjects)
   {
       // Print the tag of each Horizontal Line on the chart
       Print(String.Format("Horizontal Line {0} found.", line.Tag));
   }
}

```

An obstacle arises with traditional typecasting in a compiled assembly, since the **NinjaScript** type you attempt to cast will be present in both your DLL and **NinjaTrader**'s **Custom.dll** assembly. If you plan to compile your code into a DLL, you will need to use the [dynamic type](https://msdn.microsoft.com/en-us/library/dd264741.aspx) to avoid this conflict by dynamically assigning the type at runtime, using the guidelines below:

1. Loop through your collection using the interface type
2. Use **ToString()** to check the fully qualified namespace of the object in the loop
3. Cast the object to **dynamic**, and reference properties of that object assuming it is the expected type

```jsx-150469391 csharp
foreach (IDrawingTool line in DrawObjects.ToList())
{
   // Use ToString().Equals() to detect the object's Type
   if (line.ToString().Equals("NinjaTrader.NinjaScript.DrawingTools.HorizontalLine"))
   {
       // Cast line as dynamic and access the object by assuming that it is the Type we expect
       Print(String.Format("Horizontal Line {0} detected!", (line as dynamic).Tag));
   }
}

```

The above dynamic approach will work for primitive types. For instantiating more complex types / classes though, such as adding a new [PriceLevel](https://developer.ninjatrader.com/docs/desktop/pricelevels) programmatically to an existing drawing tool, [Reflection](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/reflection) would need to be used.

```jsx-150469391 csharp
// Instantiating more complex types such as the PriceLevels class inside of a compiled assembly

foreach (dynamic dt in DrawObjects.ToList())
{
   if(dt.ToString().Equals("NinjaTrader.NinjaScript.DrawingTools.FibonacciRetracements"))
   {
     Type type         = dt.PriceLevels.GetType().GetGenericArguments()[0];
     Assembly assembly = type.Assembly;
     var pl           = assembly.CreateInstance(type.FullName, false, BindingFlags.CreateInstance, null, new object[] { 55.5, Brushes.Red, 2 }, new System.Globalization.CultureInfo("en-US"), new object[] {});
     dt.PriceLevels.GetType().GetMethod("Add").Invoke(dt.PriceLevels, new object[] { pl });
     this.ForceRefresh();
   }
}

```

## [Working with the dynamic type](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#working-with-the-dynamic-type)

Using dynamic variables in the technique above requires careful attention to accessing members appropriately, and thus should be avoided if you do not intend to use or distribute compiled assemblies.

- No Intelliprompt: Since the compiler cannot know which type you assume a dynamic variable to be, no Intelliprompt will be displayed to help search through type members. The same applies to **Visual Studio**'s Intellisense or similar utilities.
- No Compile Errors: For the same reason, the compiler cannot know if you are using the variable in a way not supported by its expected type, trying to access members not present in that type, or other related errors. Thus, any such errors which would be caught by the compiler when typecasting will be missed, and will result in runtime errors instead. If a runtime error were to be triggered, the error may be more difficult to interpret.

Example: If you tried to access **line.tag** (improper capitalization) in the examples above, you would receive the following errors:

- Typecasting / Compile Error: "'NinjaTrader.NinjaScript.DrawingTools.HorizontalLine' does not contain a definition for 'tag' and no extension method accepting a first argument of type 'NinjaTrader.NinjaScript.DrawingTools.HorizontalLine' can be found (are you missing a using directive or an assembly reference?)"

- dynamic / Runtime Error: "Error on calling 'OnBarUpdate' method on bar 0: 'NinjaTrader.NinjaScript.DrawingTools.DrawingTool.tag' is inaccessible due to its protection level"


## [Adding XAML and Other Files Into a DLL](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#adding-xaml-and-other-files-into-a-dll)

When [exporting a compiled assembly](https://developer.ninjatrader.com/docs/desktop/export) through **NinjaTrader**, no additional resource files can be added. There are two ways around this. The first is to export the DLL from **NinjaTrader**, then open the exported .zip file, add any additional files, and re-zip the archive, but this will result in your resource files being fully accessible to end users. The second and recommended approach is to use a fully featured IDE such as **Visual Studio** to build your DLL's.

For more information on how to accomplish this with **Visual Studio**, see the "AddOn Development Environment" section of the [AddOn Development Overview](https://developer.ninjatrader.com/docs/desktop/addon_development_overview) page. Although the page focuses on AddOn development, the sample project it provides can be used to develop other **NinjaScript** types, as well.

## [Exporting custom drawing tools as assembly / DLL](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#exporting-custom-drawing-tools-as-assembly-/-dll)

## Warning

When planning to distribute your custom drawing tools via assemblies, please understand **it's paramount that you implement your own Draw method** to allow the drawing tool getting called programmatically by other **NinjaScript** objects.

The **NinjaTrader** default drawing tools would implement this via a partial class, for example you would see -

```jsx-150469391 csharp
// Default NinjaTrader drawing tool Draw. method handling

public static partial class Draw
{
}

```

However since partial classes could not span across two assemblies, therefore a custom non partial **Draw** method for your **NinjaScript** drawing tool would be needed.

```jsx-150469391 csharp
// Custom drawing tool Draw. method handling

public static class MyDrawCustom
{
}

```

## [Exports might not be backwards compatible](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#exports-might-not-be-backwards-compatible)

**NinjaScript** exports might not be backwards compatible with previous versions of **NinjaTrader**.

This is known to happen every time a new type (e.g. Enum) was introduced, since the newly introduced types are not known to prior releases of **NinjaTrader**.

Typically an error message like the following would be seen:

> "Error on calling 'SetState' method: Could not load type 'NinjaTrader.NinjaScript.Indicators.CumulativeDeltaType' from assembly 'NinjaTrader.Vendor, Version=8.0.12.0, Culture=neutral, PublicKeyToken=null'."

## [Using Compiled Assemblies](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#using-compiled-assemblies)

Compiled assemblies (DLL's) allow you to bundle your scripts into a format that hides your proprietary code along with any supporting resources. Compiled assemblies provide distinct benefits, especially for commercially distributed code, but there are a few considerations to keep in mind. Typecasting and building resource files (sounds, images, etc.) into your assemblies must be approached differently to ensure cleanly packaged, error-free DLL's.

## [Using Custom enum Properties](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#using-custom-enum-properties)

When creating custom enum properties, it is advised to create the enum outside of your **NinjaScript** class, and designating it in its own fully qualified namespace. For an example, please see [here](https://developer.ninjatrader.com/docs/desktop/creating_a_user_defined_parameter_type_enum). When using the enum in code, please use the fully qualified namespace as opposed to using a using directive to shorthand the expression.

## [Casting Types in a DLL (Using dynamic Types)](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#casting-types-in-a-dll-(using-dynamic-types))

Sometimes, you may need to cast your objects to **NinjaScript** types, such as when iterating through the **DrawObjects** collection to obtain a reference to a particular Drawing Object on a chart. When running **C#** code which has not been compiled into an assembly, typecasting can be done normally, as in the example below:

```jsx-150469391 csharp
// Typecasting in code outside of a compiled assembly

protected override void OnBarUpdate()
{
   foreach(HorizontalLine line in DrawObjects)
   {
       // Print the tag of each Horizontal Line on the chart
       Print(String.Format("Horizontal Line {0} found.", line.Tag));
   }
}

```

An obstacle arises with traditional typecasting in a compiled assembly, since the **NinjaScript** type you attempt to cast will be present in both your DLL and **NinjaTrader**'s **Custom.dll** assembly. If you plan to compile your code into a DLL, you will need to use the [dynamic type](https://msdn.microsoft.com/en-us/library/dd264741.aspx) to avoid this conflict by dynamically assigning the type at runtime, using the guidelines below:

1. Loop through your collection using the interface type
2. Use **ToString()** to check the fully qualified namespace of the object in the loop
3. Cast the object to **dynamic**, and reference properties of that object assuming it is the expected type

```jsx-150469391 csharp
foreach (IDrawingTool line in DrawObjects.ToList())
{
   // Use ToString().Equals() to detect the object's Type
   if (line.ToString().Equals("NinjaTrader.NinjaScript.DrawingTools.HorizontalLine"))
   {
       // Cast line as dynamic and access the object by assuming that it is the Type we expect
       Print(String.Format("Horizontal Line {0} detected!", (line as dynamic).Tag));
   }
}

```

The above dynamic approach will work for primitive types. For instantiating more complex types / classes though, such as adding a new [PriceLevel](https://developer.ninjatrader.com/docs/desktop/pricelevels) programmatically to an existing drawing tool, [Reflection](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/reflection) would need to be used.

```jsx-150469391 csharp
// Instantiating more complex types such as the PriceLevels class inside of a compiled assembly

foreach (dynamic dt in DrawObjects.ToList())
{
   if(dt.ToString().Equals("NinjaTrader.NinjaScript.DrawingTools.FibonacciRetracements"))
   {
     Type type         = dt.PriceLevels.GetType().GetGenericArguments()[0];
     Assembly assembly = type.Assembly;
     var pl           = assembly.CreateInstance(type.FullName, false, BindingFlags.CreateInstance, null, new object[] { 55.5, Brushes.Red, 2 }, new System.Globalization.CultureInfo("en-US"), new object[] {});
     dt.PriceLevels.GetType().GetMethod("Add").Invoke(dt.PriceLevels, new object[] { pl });
     this.ForceRefresh();
   }
}

```

## [Working with the dynamic type](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#working-with-the-dynamic-type)

Using dynamic variables in the technique above requires careful attention to accessing members appropriately, and thus should be avoided if you do not intend to use or distribute compiled assemblies.

- No Intelliprompt: Since the compiler cannot know which type you assume a dynamic variable to be, no Intelliprompt will be displayed to help search through type members. The same applies to **Visual Studio**'s Intellisense or similar utilities.
- No Compile Errors: For the same reason, the compiler cannot know if you are using the variable in a way not supported by its expected type, trying to access members not present in that type, or other related errors. Thus, any such errors which would be caught by the compiler when typecasting will be missed, and will result in runtime errors instead. If a runtime error were to be triggered, the error may be more difficult to interpret.

Example: If you tried to access **line.tag** (improper capitalization) in the examples above, you would receive the following errors:

- Typecasting / Compile Error: "'NinjaTrader.NinjaScript.DrawingTools.HorizontalLine' does not contain a definition for 'tag' and no extension method accepting a first argument of type 'NinjaTrader.NinjaScript.DrawingTools.HorizontalLine' can be found (are you missing a using directive or an assembly reference?)"

- dynamic / Runtime Error: "Error on calling 'OnBarUpdate' method on bar 0: 'NinjaTrader.NinjaScript.DrawingTools.DrawingTool.tag' is inaccessible due to its protection level"


## [Adding XAML and Other Files Into a DLL](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#adding-xaml-and-other-files-into-a-dll)

When [exporting a compiled assembly](https://developer.ninjatrader.com/docs/desktop/export) through **NinjaTrader**, no additional resource files can be added. There are two ways around this. The first is to export the DLL from **NinjaTrader**, then open the exported .zip file, add any additional files, and re-zip the archive, but this will result in your resource files being fully accessible to end users. The second and recommended approach is to use a fully featured IDE such as **Visual Studio** to build your DLL's.

For more information on how to accomplish this with **Visual Studio**, see the "AddOn Development Environment" section of the [AddOn Development Overview](https://developer.ninjatrader.com/docs/desktop/addon_development_overview) page. Although the page focuses on AddOn development, the sample project it provides can be used to develop other **NinjaScript** types, as well.

## [Exporting custom drawing tools as assembly / DLL](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#exporting-custom-drawing-tools-as-assembly-/-dll)

## Warning

When planning to distribute your custom drawing tools via assemblies, please understand **it's paramount that you implement your own Draw method** to allow the drawing tool getting called programmatically by other **NinjaScript** objects.

The **NinjaTrader** default drawing tools would implement this via a partial class, for example you would see -

```jsx-150469391 csharp
// Default NinjaTrader drawing tool Draw. method handling

public static partial class Draw
{
}

```

However since partial classes could not span across two assemblies, therefore a custom non partial **Draw** method for your **NinjaScript** drawing tool would be needed.

```jsx-150469391 csharp
// Custom drawing tool Draw. method handling

public static class MyDrawCustom
{
}

```

## [Exports might not be backwards compatible](https://developer.ninjatrader.com/docs/desktop/considerations_for_compiled_assemblies\#exports-might-not-be-backwards-compatible)

**NinjaScript** exports might not be backwards compatible with previous versions of **NinjaTrader**.

This is known to happen every time a new type (e.g. Enum) was introduced, since the newly introduced types are not known to prior releases of **NinjaTrader**.

Typically an error message like the following would be seen:

> "Error on calling 'SetState' method: Could not load type 'NinjaTrader.NinjaScript.Indicators.CumulativeDeltaType' from assembly 'NinjaTrader.Vendor, Version=8.0.12.0, Culture=neutral, PublicKeyToken=null'."