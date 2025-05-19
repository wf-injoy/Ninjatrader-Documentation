## [Definition](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#definition)

A custom **TypeConverter** class handling the designed behavior of an indicator's property descriptor collection. Use this as a base class for any custom TypeConverter you are applying to an indicator class.

## Note

- A working NinjaScript demo can be found through the reference sample on " [Using a TypeConverter to Customize Property Grid Behavior](http://ninjatrader.com/support/forum/showthread.php?t=97919)"
- When applying the custom converter, you must fully qualify the name (e.g., "NinjaTrader.NinjaScript.Indicators.MyCustomConveter")
- Additional TypeConverter information can be found from the [MSDN documentation](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter%28v=vs.110%29.aspx)
- See also **TypeConverterAttribute**
- For Strategies, see the **StrategyBaseConverter** class

## [Relevant base methods](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#relevant-base-methods)

| Method | Description |
| --- | --- |
| [TypeConverter.GetProperties()](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter.getproperties(v=vs.110).aspx) | When overriding GetProperties(), calling base.GetProperties() ensures that all default property grid behavior works as designed |
| [TypeConverter.GetPropertiesSupported()](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter.getpropertiessupported(v=vs.110).aspx) | In your custom converter class, you must override GetPropertiesSupported() and return a value of true in order for your custom type converter to work |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#syntax)

`public class IndicatorBaseConverter : TypeConverter`

## Warning

Failure to apply a type of `IndicatorBaseConverter` on an indicator class can result in unpredictable behavior of the standard NinjaTrader WPF property grid.

## Note

Tip: Common indicator functions like `Print()` are not available to a type converter instance. To debug a type converter class, you can use the AddOn **Debug Concepts** or **attach to a debugger** (recommended).

## [Examples](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#examples)

```jsx-150469391 csharp
// This namespace holds Indicators in this folder and is required. Do not change it.
namespace NinjaTrader.NinjaScript.Indicators
{
    // When applying the type converter, you must fully qualify the name
    [TypeConverter("NinjaTrader.NinjaScript.Indicators.MyCustomConveter")]
    public class MyCustomIndicator : Indicator
    {
        protected override void OnStateChange()
        {
            if (State == State.SetDefaults)
            {
                Name = "MyCustomIndicator";
            }
        }

        protected override void OnBarUpdate()
        {
            // Add your custom indicator logic here.
        }
    }

    public class MyCustomConveter : IndicatorBaseConverter
    {
        // A general TypeConveter method used for converting types
        public override PropertyDescriptorCollection GetProperties(ITypeDescriptorContext context, object component, Attribute[] attrs)
        {
            // sometimes you may need the indicator instance which actually exists on the grid
            MyCustomIndicator indicator = component as MyCustomIndicator;

            // base.GetProperties ensures we have all the properties (and associated property grid editors)
            // NinjaTrader internal logic handles for a given indicator
            PropertyDescriptorCollection propertyDescriptorCollection = base.GetPropertiesSupported(context)
                ? base.GetProperties(context, component, attrs) : TypeDescriptor.GetProperties(component, attrs);

            if (indicator == null || propertyDescriptorCollection == null)
                return propertyDescriptorCollection;

            // example of why you may need the instance that exists on the grid....
            if (indicator.EntryHandling == EntryHandling.UniqueEntries)
            {
                // do something in the event a property contains some value...
            }

            // Loop all of the properties of the indicator
            foreach (PropertyDescriptor property in propertyDescriptorCollection)
            {
                // do something with a specific property

                // cannot call **Print()** here
                // but you can call the static Output window "Process()"
                NinjaTrader.Code.Output.Process(property.Name, PrintTo.OutputTab1);
            }

            // must return the collection after making changes
            return propertyDescriptorCollection;
        }

        // Important: This must return true otherwise the type converter will not be called
        public override bool GetPropertiesSupported(ITypeDescriptorContext context)
        { return true; }
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#definition)

A custom **TypeConverter** class handling the designed behavior of an indicator's property descriptor collection. Use this as a base class for any custom TypeConverter you are applying to an indicator class.

## Note

- A working NinjaScript demo can be found through the reference sample on " [Using a TypeConverter to Customize Property Grid Behavior](http://ninjatrader.com/support/forum/showthread.php?t=97919)"
- When applying the custom converter, you must fully qualify the name (e.g., "NinjaTrader.NinjaScript.Indicators.MyCustomConveter")
- Additional TypeConverter information can be found from the [MSDN documentation](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter%28v=vs.110%29.aspx)
- See also **TypeConverterAttribute**
- For Strategies, see the **StrategyBaseConverter** class

## [Relevant base methods](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#relevant-base-methods)

| Method | Description |
| --- | --- |
| [TypeConverter.GetProperties()](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter.getproperties(v=vs.110).aspx) | When overriding GetProperties(), calling base.GetProperties() ensures that all default property grid behavior works as designed |
| [TypeConverter.GetPropertiesSupported()](https://msdn.microsoft.com/en-us/library/system.componentmodel.typeconverter.getpropertiessupported(v=vs.110).aspx) | In your custom converter class, you must override GetPropertiesSupported() and return a value of true in order for your custom type converter to work |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#syntax)

`public class IndicatorBaseConverter : TypeConverter`

## Warning

Failure to apply a type of `IndicatorBaseConverter` on an indicator class can result in unpredictable behavior of the standard NinjaTrader WPF property grid.

## Note

Tip: Common indicator functions like `Print()` are not available to a type converter instance. To debug a type converter class, you can use the AddOn **Debug Concepts** or **attach to a debugger** (recommended).

## [Examples](https://developer.ninjatrader.com/docs/desktop/indicatorbaseconverter\#examples)

```jsx-150469391 csharp
// This namespace holds Indicators in this folder and is required. Do not change it.
namespace NinjaTrader.NinjaScript.Indicators
{
    // When applying the type converter, you must fully qualify the name
    [TypeConverter("NinjaTrader.NinjaScript.Indicators.MyCustomConveter")]
    public class MyCustomIndicator : Indicator
    {
        protected override void OnStateChange()
        {
            if (State == State.SetDefaults)
            {
                Name = "MyCustomIndicator";
            }
        }

        protected override void OnBarUpdate()
        {
            // Add your custom indicator logic here.
        }
    }

    public class MyCustomConveter : IndicatorBaseConverter
    {
        // A general TypeConveter method used for converting types
        public override PropertyDescriptorCollection GetProperties(ITypeDescriptorContext context, object component, Attribute[] attrs)
        {
            // sometimes you may need the indicator instance which actually exists on the grid
            MyCustomIndicator indicator = component as MyCustomIndicator;

            // base.GetProperties ensures we have all the properties (and associated property grid editors)
            // NinjaTrader internal logic handles for a given indicator
            PropertyDescriptorCollection propertyDescriptorCollection = base.GetPropertiesSupported(context)
                ? base.GetProperties(context, component, attrs) : TypeDescriptor.GetProperties(component, attrs);

            if (indicator == null || propertyDescriptorCollection == null)
                return propertyDescriptorCollection;

            // example of why you may need the instance that exists on the grid....
            if (indicator.EntryHandling == EntryHandling.UniqueEntries)
            {
                // do something in the event a property contains some value...
            }

            // Loop all of the properties of the indicator
            foreach (PropertyDescriptor property in propertyDescriptorCollection)
            {
                // do something with a specific property

                // cannot call **Print()** here
                // but you can call the static Output window "Process()"
                NinjaTrader.Code.Output.Process(property.Name, PrintTo.OutputTab1);
            }

            // must return the collection after making changes
            return propertyDescriptorCollection;
        }

        // Important: This must return true otherwise the type converter will not be called
        public override bool GetPropertiesSupported(ITypeDescriptorContext context)
        { return true; }
    }
}

```