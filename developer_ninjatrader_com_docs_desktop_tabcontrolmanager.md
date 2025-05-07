## [Definition](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#definition)

The **TabControlManager** class can be used to set or check several properties of a [TabControl](https://developer.ninjatrader.com/docs/desktop/tabcontrol). Rather than instantiating a **TabControlManager** object, you can use the public static methods of the class to set specific properties for a specified **TabControl**, as in the example code below.

## Note

Note: For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Setters](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#setters)

| Method | Description |
| --- | --- |
| **SetCanAddTabs(DependencyObject obj, bool value)** | Sets a TabControl can add new tabs |
| **SetCanDuplicateTabs(DependencyObject obj, bool value)** | Sets a TabControl can duplicate tabs in new tabs or new windows |
| **SetCanRemoveTabs(DependencyObject obj, bool value)** | Sets a TabControl can remove tabs |
| **SetFactory(DependencyObject obj, bool value)** | Sets the NTTabFactory for the TabControl |
| **SetIsSimulation(DependencyObject obj, bool value)** | Sets the current NTTabPage to the simulation color if true. This method needs to be used logically from within your NTTabPage. |
| **SetIsMovable(DependencyObject obj, bool value)** | Sets a TabControl allows changing the order of tabs in a window |

## [Getters](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#getters)

| Method | Description |
| --- | --- |
| **GetCanAddTabs(DependencyObject obj)** | Indicates a TabControl can add new tabs |
| **GetCanDuplicateTabs(DependencyObject obj)** | Indicates a TabControl can duplicate tabs in new tabs or new windows |
| **GetCanRemoveTabs(DependencyObject obj)** | Indicates a TabControl can remove tabs |
| **GetFactory(DependencyObject obj)** | Obtains the NTTabFactory used by a TabControl |
| **GetIsSimulation(DependencyObject obj)** | Indicates the Simulation Color selected in the Options menu is visible in the tab background when a simulation account is selected in the tab |
| **GetIsMovable(DependencyObject obj)** | Indicates a TabControl allows changing the order of tabs in a window |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#examples)

```jsx-150469391 csharp
public AddOnFrameworkWindow()
{
   // TabControl should be created for window content if tab features are wanted
   TabControl tc = new TabControl();

   // Attached properties defined in TabControlManager class should be set to achieve tab moving, adding/removing tabs
   TabControlManager.SetIsMovable(tc, true);
   TabControlManager.SetCanAddTabs(tc, true);
   TabControlManager.SetCanRemoveTabs(tc, true);

   // if ability to add new tabs is desired, TabControl has to have attached property "Factory" set.
   TabControlManager.SetFactory(tc, new AddOnFrameworkWindowFactory());
   Content = tc;

   /* In order to have link buttons functionality, tab control items must be derived from Tools.NTTabPage
    They can be added using extention method AddNTTabPage(NTTabPage page) */
   tc.AddNTTabPage(new AddOnFrameworkTab());
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#definition)

The **TabControlManager** class can be used to set or check several properties of a [TabControl](https://developer.ninjatrader.com/docs/desktop/tabcontrol). Rather than instantiating a **TabControlManager** object, you can use the public static methods of the class to set specific properties for a specified **TabControl**, as in the example code below.

## Note

Note: For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Setters](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#setters)

| Method | Description |
| --- | --- |
| **SetCanAddTabs(DependencyObject obj, bool value)** | Sets a TabControl can add new tabs |
| **SetCanDuplicateTabs(DependencyObject obj, bool value)** | Sets a TabControl can duplicate tabs in new tabs or new windows |
| **SetCanRemoveTabs(DependencyObject obj, bool value)** | Sets a TabControl can remove tabs |
| **SetFactory(DependencyObject obj, bool value)** | Sets the NTTabFactory for the TabControl |
| **SetIsSimulation(DependencyObject obj, bool value)** | Sets the current NTTabPage to the simulation color if true. This method needs to be used logically from within your NTTabPage. |
| **SetIsMovable(DependencyObject obj, bool value)** | Sets a TabControl allows changing the order of tabs in a window |

## [Getters](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#getters)

| Method | Description |
| --- | --- |
| **GetCanAddTabs(DependencyObject obj)** | Indicates a TabControl can add new tabs |
| **GetCanDuplicateTabs(DependencyObject obj)** | Indicates a TabControl can duplicate tabs in new tabs or new windows |
| **GetCanRemoveTabs(DependencyObject obj)** | Indicates a TabControl can remove tabs |
| **GetFactory(DependencyObject obj)** | Obtains the NTTabFactory used by a TabControl |
| **GetIsSimulation(DependencyObject obj)** | Indicates the Simulation Color selected in the Options menu is visible in the tab background when a simulation account is selected in the tab |
| **GetIsMovable(DependencyObject obj)** | Indicates a TabControl allows changing the order of tabs in a window |

## [Examples](https://developer.ninjatrader.com/docs/desktop/tabcontrolmanager\#examples)

```jsx-150469391 csharp
public AddOnFrameworkWindow()
{
   // TabControl should be created for window content if tab features are wanted
   TabControl tc = new TabControl();

   // Attached properties defined in TabControlManager class should be set to achieve tab moving, adding/removing tabs
   TabControlManager.SetIsMovable(tc, true);
   TabControlManager.SetCanAddTabs(tc, true);
   TabControlManager.SetCanRemoveTabs(tc, true);

   // if ability to add new tabs is desired, TabControl has to have attached property "Factory" set.
   TabControlManager.SetFactory(tc, new AddOnFrameworkWindowFactory());
   Content = tc;

   /* In order to have link buttons functionality, tab control items must be derived from Tools.NTTabPage
    They can be added using extention method AddNTTabPage(NTTabPage page) */
   tc.AddNTTabPage(new AddOnFrameworkTab());
}

```