## [Definition](https://developer.ninjatrader.com/docs/desktop/ntmenuitem\#definition)

**NTMenuItem** is used to create new menu entries. For example, an instance of this class can be placed in an existing Control Center menu to launch an [**NTWindow**](https://developer.ninjatrader.com/docs/desktop/ntwindow) as part of an AddOn, as seen in the example code below.

## Note

For a complete, working example of this class in use, download the framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/ntmenuitem\#examples)

```jsx-150469391 csharp
private NTMenuItem myNewMenuItem;
private NTMenuItem existingControlCenterNewMenu;

protected override void OnWindowCreated(Window window)
{
    // We want to place the menu item for the AddOn in the Control Center's "New" menu
    // First obtain a reference to the Control Center window
    ControlCenter cc = window as ControlCenter;
    if (cc == null)
        return;

    /* Determine we want to place the AddOn in the Control Center's "New" menu
    Other menus can be accessed via the control's "Automation ID". For example: toolsMenuItem, workspacesMenuItem, connectionsMenuItem, helpMenuItem. */
    existingControlCenterNewMenu = cc.FindFirst("ControlCenterMenuItemNew") as NTMenuItem;
    if (existingControlCenterNewMenu == null)
        return;

    // Instantiate myNewMenuItem
    // 'Header' sets the name of our AddOn seen in the menu structure. 'Style' sets the font style.
    myNewMenuItem = new NTMenuItem { Header = "AddOn Framework", Style = Application.Current.TryFindResource("MainMenuItem") as Style };

    // Add our AddOn menu item into the "New" menu
    existingControlCenterNewMenu.Items.Add(myNewMenuItem);

    // Subscribe to the event for when the user presses the menu item
    myNewMenuItem.Click += OnMenuItemClick;
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/ntmenuitem\#definition)

**NTMenuItem** is used to create new menu entries. For example, an instance of this class can be placed in an existing Control Center menu to launch an [**NTWindow**](https://developer.ninjatrader.com/docs/desktop/ntwindow) as part of an AddOn, as seen in the example code below.

## Note

For a complete, working example of this class in use, download the framework example located on our [Developing AddOns Overview](https://developer.ninjatrader.com/docs/desktop/developing_add_ons).

## [Examples](https://developer.ninjatrader.com/docs/desktop/ntmenuitem\#examples)

```jsx-150469391 csharp
private NTMenuItem myNewMenuItem;
private NTMenuItem existingControlCenterNewMenu;

protected override void OnWindowCreated(Window window)
{
    // We want to place the menu item for the AddOn in the Control Center's "New" menu
    // First obtain a reference to the Control Center window
    ControlCenter cc = window as ControlCenter;
    if (cc == null)
        return;

    /* Determine we want to place the AddOn in the Control Center's "New" menu
    Other menus can be accessed via the control's "Automation ID". For example: toolsMenuItem, workspacesMenuItem, connectionsMenuItem, helpMenuItem. */
    existingControlCenterNewMenu = cc.FindFirst("ControlCenterMenuItemNew") as NTMenuItem;
    if (existingControlCenterNewMenu == null)
        return;

    // Instantiate myNewMenuItem
    // 'Header' sets the name of our AddOn seen in the menu structure. 'Style' sets the font style.
    myNewMenuItem = new NTMenuItem { Header = "AddOn Framework", Style = Application.Current.TryFindResource("MainMenuItem") as Style };

    // Add our AddOn menu item into the "New" menu
    existingControlCenterNewMenu.Items.Add(myNewMenuItem);

    // Subscribe to the event for when the user presses the menu item
    myNewMenuItem.Click += OnMenuItemClick;
}

```