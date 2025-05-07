If you wish to have tab page functionality like adding, removing, moving, duplicating tabs you must create a class which implements the **INTTabFactory** interface.

This interface contains two methods which must be hidden:

## [Syntax](https://developer.ninjatrader.com/docs/desktop/inttabfactory_interface\#syntax)

`NTWindow CreateParentWindow()`

`NTTabPage CreateTabPage(string typeName, bool isNewWindow = false)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/inttabfactory_interface\#examples)

```jsx-150469391 csharp
public class MyWindowFactory : INTTabFactory
{
     // INTTabFactory member. Creates the parent window that contains tabs
     public NTWindow CreateParentWindow()
     {
         return new MyWindow();
     }

     // INTTabFactory member. Creates new tab pages whenever the user presses the + button
     public NTTabPage CreateTabPage(string typeName)
     {
         return new MyWindowTabPage();
     }
}

```

If you wish to have tab page functionality like adding, removing, moving, duplicating tabs you must create a class which implements the **INTTabFactory** interface.

This interface contains two methods which must be hidden:

## [Syntax](https://developer.ninjatrader.com/docs/desktop/inttabfactory_interface\#syntax)

`NTWindow CreateParentWindow()`

`NTTabPage CreateTabPage(string typeName, bool isNewWindow = false)`

## [Examples](https://developer.ninjatrader.com/docs/desktop/inttabfactory_interface\#examples)

```jsx-150469391 csharp
public class MyWindowFactory : INTTabFactory
{
     // INTTabFactory member. Creates the parent window that contains tabs
     public NTWindow CreateParentWindow()
     {
         return new MyWindow();
     }

     // INTTabFactory member. Creates new tab pages whenever the user presses the + button
     public NTTabPage CreateTabPage(string typeName)
     {
         return new MyWindowTabPage();
     }
}

```