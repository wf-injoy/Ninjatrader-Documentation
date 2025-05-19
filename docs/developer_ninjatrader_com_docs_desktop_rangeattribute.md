## [Definition](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#definition)

Determines if the value of the following declared property is valid within a specified range. These values are checked when the NinjaScript object has reached **State.Configure**. For configuration through the UI (e.g., the user has selected Apply or OK to configure the value from the indicator dialog box) and determines to be invalid, the value will be automatically rounded to the nearest minimum or maximum value. Should the property be set as a **NinjaScriptAttribute** and called from a hosting NinjaScript object and determines to be invalid, an exception will be thrown and the hosted indicator will NOT execute.

## Note

The RangeAttribute object is a general purpose attribute made available from the .NET Framework. The information on this page is written to demonstrate how you may use this object within NinjaScript conventions used for the NinjaTrader UI's property grid (e.g., an indicator dialog). There are more methods and properties that you can learn about from MSDN's [RangeAttribute Class](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.rangeattribute(v=vs.110).aspx) which are NOT covered in this topic; as such there is NO guarantee they will work with the NinjaTrader UI's property grids.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#syntax)

`[Range(int minimum, int maximum)]`

`[Range(double minimum, double maximum)]`

`[Range(type type, string minimum, string maximum)]`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#parameters)

| maximum | Defines the highest allowed value the user can set for the property |
| minimum | Defines the lowest allowed value the user can set for the property |
| type | The **type** of object to test |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#examples)

```jsx-150469391 csharp
#region Properties
// set range between 1 and the highest possible integer
[Range(1, int.MaxValue)]
public int Myint
{ get; set; }

//set range between .001 and 1
[Range(.001, 1.0)]
public double MyDouble
{ get; set; }

// set range as a type DateTime between these dates
[Range(typeof(DateTime), "01/01/1990", "12/31/2015")]
public DateTime MyTime
{ get; set; }
//#endregion

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#definition)

Determines if the value of the following declared property is valid within a specified range. These values are checked when the NinjaScript object has reached **State.Configure**. For configuration through the UI (e.g., the user has selected Apply or OK to configure the value from the indicator dialog box) and determines to be invalid, the value will be automatically rounded to the nearest minimum or maximum value. Should the property be set as a **NinjaScriptAttribute** and called from a hosting NinjaScript object and determines to be invalid, an exception will be thrown and the hosted indicator will NOT execute.

## Note

The RangeAttribute object is a general purpose attribute made available from the .NET Framework. The information on this page is written to demonstrate how you may use this object within NinjaScript conventions used for the NinjaTrader UI's property grid (e.g., an indicator dialog). There are more methods and properties that you can learn about from MSDN's [RangeAttribute Class](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.rangeattribute(v=vs.110).aspx) which are NOT covered in this topic; as such there is NO guarantee they will work with the NinjaTrader UI's property grids.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#syntax)

`[Range(int minimum, int maximum)]`

`[Range(double minimum, double maximum)]`

`[Range(type type, string minimum, string maximum)]`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#parameters)

| maximum | Defines the highest allowed value the user can set for the property |
| minimum | Defines the lowest allowed value the user can set for the property |
| type | The **type** of object to test |

## [Examples](https://developer.ninjatrader.com/docs/desktop/rangeattribute\#examples)

```jsx-150469391 csharp
#region Properties
// set range between 1 and the highest possible integer
[Range(1, int.MaxValue)]
public int Myint
{ get; set; }

//set range between .001 and 1
[Range(.001, 1.0)]
public double MyDouble
{ get; set; }

// set range as a type DateTime between these dates
[Range(typeof(DateTime), "01/01/1990", "12/31/2015")]
public DateTime MyTime
{ get; set; }
//#endregion

```