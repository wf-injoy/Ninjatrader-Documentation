User definable inputs do not need to be limited to numeric values. You can have brushes as an input as well. To do this you will need to make a public property for a Brush object instead of an int or double.

In the "Properties" region of your code, there is only a slight change in the code snippet you would normally use to create user definable inputs.

```jsx-150469391 csharp
[XmlIgnore()]
[Display(Name = "BorderBrush", GroupName = "NinjaScriptParameters", Order = 0)]

```

The second difference is in the next line of code:

```jsx-150469391 csharp
public Brush BorderBrush
{ get; set; }

```

This creates a brush input for use in the dialog window when we try to add the NinjaScript to a chart.

Some additional extra code that is required for creating a color input is to serialize the brush. Serialization is necessary for NinjaTrader to use the brush input throughout the program. Please note that serialization is a general concept not exclusive to brush inputs. There may be other struct/classes (for a TimeSpan example, please cross reference this page) that you could use in your code that would also need to have their "value" properties serialized.

```jsx-150469391 csharp
[Browsable(false)]
public string BorderBrushSerialize
{
get { return Serialize.BrushToString(BorderBrush); }
  set { BorderBrush = Serialize.StringToBrush(value); }
}

```

Attached is a NinjaScript indicator sample that uses two user definable brush inputs to determine the color of a drawn rectangle.

[SampleBrushInput.zip](https://ninjatrader.com/support/helpGuides/nt8/samples/SampleBrushInput.zip)

User definable inputs do not need to be limited to numeric values. You can have brushes as an input as well. To do this you will need to make a public property for a Brush object instead of an int or double.

In the "Properties" region of your code, there is only a slight change in the code snippet you would normally use to create user definable inputs.

```jsx-150469391 csharp
[XmlIgnore()]
[Display(Name = "BorderBrush", GroupName = "NinjaScriptParameters", Order = 0)]

```

The second difference is in the next line of code:

```jsx-150469391 csharp
public Brush BorderBrush
{ get; set; }

```

This creates a brush input for use in the dialog window when we try to add the NinjaScript to a chart.

Some additional extra code that is required for creating a color input is to serialize the brush. Serialization is necessary for NinjaTrader to use the brush input throughout the program. Please note that serialization is a general concept not exclusive to brush inputs. There may be other struct/classes (for a TimeSpan example, please cross reference this page) that you could use in your code that would also need to have their "value" properties serialized.

```jsx-150469391 csharp
[Browsable(false)]
public string BorderBrushSerialize
{
get { return Serialize.BrushToString(BorderBrush); }
  set { BorderBrush = Serialize.StringToBrush(value); }
}

```

Attached is a NinjaScript indicator sample that uses two user definable brush inputs to determine the color of a drawn rectangle.

[SampleBrushInput.zip](https://ninjatrader.com/support/helpGuides/nt8/samples/SampleBrushInput.zip)