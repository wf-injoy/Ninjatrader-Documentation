## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#definition)

AtmStrategySelector is an UI element users can interact with for selecting ATM Strategies.

## [Events and Properties](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#events-and-properties)

| Cleanup() | Disposes of the AtmStrategySelector (Note: calling the **NTTabPage base.Cleanup()** is sufficient to clean up this control) |
| CustomPropertiesChanged | Event handler for when properties have changed on the ATM strategy |
| Id | A string identifying the ATM Strategy selector |
| SelectedAtmStrategy | Returns an AtmStrategy representing the selected ATM strategy |
| SelectionChanged | Event handler for when the selected ATM strategy has changed |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#examples)

This example demonstrates how to use the ATM strategy selector and properly link its behavior with the quantity up/down and TIF selectors.

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#examples)

```jsx-150469391 csharp
private QuantityUpDown qudSelector;
private TifSelector tifSelector;
private AtmStrategy.AtmStrategySelector atmStrategySelector;

private DependencyObject LoadXAML()
{
    qudSelector = LogicalTreeHelper.FindLogicalNode(pageContent, "qudSelector") as QuantityUpDown;
    tifSelector = LogicalTreeHelper.FindLogicalNode(pageContent, "tifSelector") as TifSelector;
    tifSelector.SetBinding(TifSelector.AccountProperty, new Binding { Source = accountSelector, Path = new PropertyPath("SelectedAccount") });
    tifSelector.SelectionChanged += (o, args) =>
    {
        if (atmStrategySelector.SelectedAtmStrategy != null)
            atmStrategySelector.SelectedAtmStrategy.TimeInForce = tifSelector.SelectedTif;
    };
    atmStrategySelector = LogicalTreeHelper.FindLogicalNode(pageContent, "atmStrategySelector") as AtmStrategy.AtmStrategySelector;
    atmStrategySelector.Id = Guid.NewGuid().ToString("N");
    if (atmStrategySelector != null)
        atmStrategySelector.CustomPropertiesChanged += OnAtmCustomPropertiesChanged;
    atmStrategySelector.SetBinding(AtmStrategy.AtmStrategySelector.AccountProperty, new Binding { Source = accountSelector, Path = new PropertyPath("SelectedAccount") });
    atmStrategySelector.SelectionChanged += (o, args) =>
    {
        if (atmStrategySelector.SelectedItem == null)
            return;
        if (args.AddedItems.Count > 0)
        {
            AtmStrategy selectedAtmStrategy = args.AddedItems[0] as AtmStrategy;
            if (selectedAtmStrategy != null)
                tifSelector.SelectedTif = selectedAtmStrategy.TimeInForce;
        }
    };
}

private void OnAtmCustomPropertiesChanged(object sender, NinjaScript.AtmStrategy.CustomPropertiesChangedEventArgs args)
{
    tifSelector.SelectedTif = args.NewTif;
    qudSelector.Value = args.NewQuantity;
}

public override void Cleanup()
{
    base.Cleanup();
}

```

```jsx-150469391 csharp
<atmstrategy:atmstrategyselector grid.column="2" grid.row="12" linkedquantity="{Binding ElementName=qudSelector, Path=Value, Mode=OneWay}" x:name="atmStrategySelector">
    <atmstrategy:atmstrategyselector.margin>
        <thickness bottom="0" left="{StaticResource MarginButtonLeft}" right="{StaticResource MarginBase}" top="{StaticResource MarginControl}"></thickness>
    </atmstrategy:atmstrategyselector.margin>
</atmstrategy:atmstrategyselector>

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#definition)

AtmStrategySelector is an UI element users can interact with for selecting ATM Strategies.

## [Events and Properties](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#events-and-properties)

| Cleanup() | Disposes of the AtmStrategySelector (Note: calling the **NTTabPage base.Cleanup()** is sufficient to clean up this control) |
| CustomPropertiesChanged | Event handler for when properties have changed on the ATM strategy |
| Id | A string identifying the ATM Strategy selector |
| SelectedAtmStrategy | Returns an AtmStrategy representing the selected ATM strategy |
| SelectionChanged | Event handler for when the selected ATM strategy has changed |

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#examples)

This example demonstrates how to use the ATM strategy selector and properly link its behavior with the quantity up/down and TIF selectors.

## [Examples](https://developer.ninjatrader.com/docs/desktop/atmstrategyselector\#examples)

```jsx-150469391 csharp
private QuantityUpDown qudSelector;
private TifSelector tifSelector;
private AtmStrategy.AtmStrategySelector atmStrategySelector;

private DependencyObject LoadXAML()
{
    qudSelector = LogicalTreeHelper.FindLogicalNode(pageContent, "qudSelector") as QuantityUpDown;
    tifSelector = LogicalTreeHelper.FindLogicalNode(pageContent, "tifSelector") as TifSelector;
    tifSelector.SetBinding(TifSelector.AccountProperty, new Binding { Source = accountSelector, Path = new PropertyPath("SelectedAccount") });
    tifSelector.SelectionChanged += (o, args) =>
    {
        if (atmStrategySelector.SelectedAtmStrategy != null)
            atmStrategySelector.SelectedAtmStrategy.TimeInForce = tifSelector.SelectedTif;
    };
    atmStrategySelector = LogicalTreeHelper.FindLogicalNode(pageContent, "atmStrategySelector") as AtmStrategy.AtmStrategySelector;
    atmStrategySelector.Id = Guid.NewGuid().ToString("N");
    if (atmStrategySelector != null)
        atmStrategySelector.CustomPropertiesChanged += OnAtmCustomPropertiesChanged;
    atmStrategySelector.SetBinding(AtmStrategy.AtmStrategySelector.AccountProperty, new Binding { Source = accountSelector, Path = new PropertyPath("SelectedAccount") });
    atmStrategySelector.SelectionChanged += (o, args) =>
    {
        if (atmStrategySelector.SelectedItem == null)
            return;
        if (args.AddedItems.Count > 0)
        {
            AtmStrategy selectedAtmStrategy = args.AddedItems[0] as AtmStrategy;
            if (selectedAtmStrategy != null)
                tifSelector.SelectedTif = selectedAtmStrategy.TimeInForce;
        }
    };
}

private void OnAtmCustomPropertiesChanged(object sender, NinjaScript.AtmStrategy.CustomPropertiesChangedEventArgs args)
{
    tifSelector.SelectedTif = args.NewTif;
    qudSelector.Value = args.NewQuantity;
}

public override void Cleanup()
{
    base.Cleanup();
}

```

```jsx-150469391 csharp
<atmstrategy:atmstrategyselector grid.column="2" grid.row="12" linkedquantity="{Binding ElementName=qudSelector, Path=Value, Mode=OneWay}" x:name="atmStrategySelector">
    <atmstrategy:atmstrategyselector.margin>
        <thickness bottom="0" left="{StaticResource MarginButtonLeft}" right="{StaticResource MarginBase}" top="{StaticResource MarginControl}"></thickness>
    </atmstrategy:atmstrategyselector.margin>
</atmstrategy:atmstrategyselector>

```