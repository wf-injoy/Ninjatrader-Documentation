## [Definition](https://developer.ninjatrader.com/docs/desktop/controlcenter\#definition)

ControlCenter is a XAML-defined class containing the layout and properties of the Control Center window. When altering the Control Center window (for example, to add a menu item into the "New" menu to launch an NTWindow as part of an AddOn, as seen in the example below), a generic reference to a Window object can be cast to **ControlCenter** specifically.

## Note

For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/controlcenter\#examples)

```jsx-150469391 csharp
private NTMenuItem ControlCenterNewMenu;

protected override void OnWindowCreated(Window window)
{
    // We want to place the menu item for the AddOn in the Control Center's "New" menu
    // First obtain a reference to the Control Center window
    ControlCenter cc = window as ControlCenter;
    if (cc == null)
        return;

    /* Determine we want to place the AddOn in the Control Center's "New" menu
    Other menus can be accessed via the control's "Automation ID". For example: toolsMenuItem, workspacesMenuItem, connectionsMenuItem, helpMenuItem. */
    ControlCenterNewMenu = cc.FindFirst("ControlCenterMenuItemNew") as NTMenuItem;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/controlcenter\#definition)

ControlCenter is a XAML-defined class containing the layout and properties of the Control Center window. When altering the Control Center window (for example, to add a menu item into the "New" menu to launch an NTWindow as part of an AddOn, as seen in the example below), a generic reference to a Window object can be cast to **ControlCenter** specifically.

## Note

For a complete, working example of this class in use, download framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/controlcenter\#examples)

```jsx-150469391 csharp
private NTMenuItem ControlCenterNewMenu;

protected override void OnWindowCreated(Window window)
{
    // We want to place the menu item for the AddOn in the Control Center's "New" menu
    // First obtain a reference to the Control Center window
    ControlCenter cc = window as ControlCenter;
    if (cc == null)
        return;

    /* Determine we want to place the AddOn in the Control Center's "New" menu
    Other menus can be accessed via the control's "Automation ID". For example: toolsMenuItem, workspacesMenuItem, connectionsMenuItem, helpMenuItem. */
    ControlCenterNewMenu = cc.FindFirst("ControlCenterMenuItemNew") as NTMenuItem;
}

```