## [Definition](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#definition)

The **OnNextDataPoint()** method is called for each line of data contained in the file being imported. This method is only called if the import type determines that the file has a valid data point, and will continue to be called until it reaches the end of the file, or until the data point is no longer valid.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#syntax)

See example below. The [NinjaScript code wizards](https://developer.ninjatrader.com/docs/desktop/ninjascript_wizard) automatically generate the method syntax for you.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#examples)

```jsx-150469391 csharp
private StreamReader reader;

protected override void OnNextDataPoint()
{
   if (reader == null)
       return;

   // Continually read data using the StreamReader defined above
   while (true)
   {
       DataPointString = reader.ReadLine();
       // Additional data formatting here
   }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#definition)

The **OnNextDataPoint()** method is called for each line of data contained in the file being imported. This method is only called if the import type determines that the file has a valid data point, and will continue to be called until it reaches the end of the file, or until the data point is no longer valid.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#syntax)

See example below. The [NinjaScript code wizards](https://developer.ninjatrader.com/docs/desktop/ninjascript_wizard) automatically generate the method syntax for you.

## [Examples](https://developer.ninjatrader.com/docs/desktop/onnextdatapoint\#examples)

```jsx-150469391 csharp
private StreamReader reader;

protected override void OnNextDataPoint()
{
   if (reader == null)
       return;

   // Continually read data using the StreamReader defined above
   while (true)
   {
       DataPointString = reader.ReadLine();
       // Additional data formatting here
   }
}

```