## [Definition](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#definition)

Called when the window is restored from a workspace, which is called after **OnWindowCreated()**. This method is used to recall any custom **XElement** data from the workspace by referencing a window. Please also see **OnWindowSaved()** for information on how to store custom **XElement** data when a window is saved.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#syntax)

`OnWindowRestored(Window window, XElement element)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#parameters)

| **window** | A [Window](https://msdn.microsoft.com/en-us/library/system.windows.window(v=vs.110).aspx) object which is being restored from a workspace |
| **element** | The [XElement](https://msdn.microsoft.com/en-us/library/system.xml.linq.xelement(v=vs.110).aspx) object representing the workspace being restored |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#examples)

```jsx-150469391 csharp

protected override void OnWindowRestored(Window window, XElement element)
{
   Print("OnWindowRestored for " + window.GetHashCode());

   // locate the worksapces "SampleAddOn" elemenet which was created and saved earlier using the OnWindowSaved() method
   XElement sampleAddOnElement = element.Element("SampleAddOn");

   // do not do anything if that element does not exist
   if (sampleAddOnElement == null)
     return;

   // loop through all the contents of the "SampleAddOn" element
   foreach (XElement content in sampleAddOnElement.Elements())
   {
       // find the "ButtonState" content, restore it's value and set that as our tracked buttonState
       if (content.Name == "ButtonState")
       {
           bool buttonState = false;
           bool.TryParse(content.Value, out buttonState);
             continue;
       }
       //Parse additional elements here
   }

   //Don't forget to call the base OnWindowRestored method after you're done.
   base.OnWindowRestored(window, element);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#definition)

Called when the window is restored from a workspace, which is called after **OnWindowCreated()**. This method is used to recall any custom **XElement** data from the workspace by referencing a window. Please also see **OnWindowSaved()** for information on how to store custom **XElement** data when a window is saved.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#syntax)

`OnWindowRestored(Window window, XElement element)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#parameters)

| **window** | A [Window](https://msdn.microsoft.com/en-us/library/system.windows.window(v=vs.110).aspx) object which is being restored from a workspace |
| **element** | The [XElement](https://msdn.microsoft.com/en-us/library/system.xml.linq.xelement(v=vs.110).aspx) object representing the workspace being restored |

## [Examples](https://developer.ninjatrader.com/docs/desktop/onwindowrestored\#examples)

```jsx-150469391 csharp

protected override void OnWindowRestored(Window window, XElement element)
{
   Print("OnWindowRestored for " + window.GetHashCode());

   // locate the worksapces "SampleAddOn" elemenet which was created and saved earlier using the OnWindowSaved() method
   XElement sampleAddOnElement = element.Element("SampleAddOn");

   // do not do anything if that element does not exist
   if (sampleAddOnElement == null)
     return;

   // loop through all the contents of the "SampleAddOn" element
   foreach (XElement content in sampleAddOnElement.Elements())
   {
       // find the "ButtonState" content, restore it's value and set that as our tracked buttonState
       if (content.Name == "ButtonState")
       {
           bool buttonState = false;
           bool.TryParse(content.Value, out buttonState);
             continue;
       }
       //Parse additional elements here
   }

   //Don't forget to call the base OnWindowRestored method after you're done.
   base.OnWindowRestored(window, element);

```