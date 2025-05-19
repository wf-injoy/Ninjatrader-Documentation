## [Definition](https://developer.ninjatrader.com/docs/desktop/tabcontrol\#definition)

The **TabControl** class provides functionality for working with **NTTabPage** objects within an **NTWindow**. **TabControl** should be instantiated within the constructor for an **NTWindow** instance, in order to configure the window to be able to host and work with tabs.

## Note

Note: For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/tabcontrol\#examples)

In the example below, we define an instance of **NTWindow**, then use **TabControl** to accomplish various setup tasks:

- Provide the **NTWindow** with the ability to add, remove, and move tabs
- Attach a Factory to the **TabControl** to handle logic for creating new tabs
- Set up the **TabControl** with the ability to utilize window linking

```jsx-150469391 csharp
public class MyWindow : NTWindow, IWorkspacePersistence
{
    public MyWindow()
    {
        // TabControl should be created for window content if tab features are wanted
        TabControl tc = new TabControl();

        // Attached properties defined in the TabControlManager class should be set to add, remove, or move tabs
        TabControlManager.SetIsMovable(tc, true);
        TabControlManager.SetCanAddTabs(tc, true);
        TabControlManager.SetCanRemoveTabs(tc, true);

        // if the ability to add new tabs is desired, TabControl must have attached property "Factory" set.
        TabControlManager.SetFactory(tc, new MyWindowFactory());
        Content = tc;

        /* In order to have link buttons functionality, tab control items must be derived from Tools.NTTabPage
         They can be added using extention method AddNTTabPage(NTTabPage page) */
        tc.AddNTTabPage(new MyTab());
    }
}

/* Class which implements Tools.INTTabFactory must be created and set as an attached property for TabControl
in order to use tab page add/remove/move/duplicate functionality */
public class MyWindowFactory : INTTabFactory
{
    // INTTabFactory member. Required to create parent window
    public NTWindow CreateParentWindow()
    {
        return new MyWindow();
    }

    // INTTabFactory member. Required to create tabs
    public NTTabPage CreateTabPage(string typeName, bool isTrue)
    {
        return new MyTab();
    }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/tabcontrol\#definition)

The **TabControl** class provides functionality for working with **NTTabPage** objects within an **NTWindow**. **TabControl** should be instantiated within the constructor for an **NTWindow** instance, in order to configure the window to be able to host and work with tabs.

## Note

Note: For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/tabcontrol\#examples)

In the example below, we define an instance of **NTWindow**, then use **TabControl** to accomplish various setup tasks:

- Provide the **NTWindow** with the ability to add, remove, and move tabs
- Attach a Factory to the **TabControl** to handle logic for creating new tabs
- Set up the **TabControl** with the ability to utilize window linking

```jsx-150469391 csharp
public class MyWindow : NTWindow, IWorkspacePersistence
{
    public MyWindow()
    {
        // TabControl should be created for window content if tab features are wanted
        TabControl tc = new TabControl();

        // Attached properties defined in the TabControlManager class should be set to add, remove, or move tabs
        TabControlManager.SetIsMovable(tc, true);
        TabControlManager.SetCanAddTabs(tc, true);
        TabControlManager.SetCanRemoveTabs(tc, true);

        // if the ability to add new tabs is desired, TabControl must have attached property "Factory" set.
        TabControlManager.SetFactory(tc, new MyWindowFactory());
        Content = tc;

        /* In order to have link buttons functionality, tab control items must be derived from Tools.NTTabPage
         They can be added using extention method AddNTTabPage(NTTabPage page) */
        tc.AddNTTabPage(new MyTab());
    }
}

/* Class which implements Tools.INTTabFactory must be created and set as an attached property for TabControl
in order to use tab page add/remove/move/duplicate functionality */
public class MyWindowFactory : INTTabFactory
{
    // INTTabFactory member. Required to create parent window
    public NTWindow CreateParentWindow()
    {
        return new MyWindow();
    }

    // INTTabFactory member. Required to create tabs
    public NTTabPage CreateTabPage(string typeName, bool isTrue)
    {
        return new MyTab();
    }
}

```