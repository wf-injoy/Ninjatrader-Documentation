## [Definition](https://developer.ninjatrader.com/docs/desktop/applyto\#definition)

Applies a custom **SimpleFont** object's properties (family, size, and style) to a [Windows Control](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control?view=windowsdesktop-9.0&redirectedfrom=MSDN).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applyto\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applyto\#syntax)

`<simplefont>.ApplyTo(DependencyObject target)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applyto\#parameters)

| Parameter | Description |
| --- | --- |
| target | The [DependencyObject](https://msdn.microsoft.com/en-us/library/system.windows.dependencyobject(v=vs.110).aspx) to apply the SimpleFont object |

## [Examples](https://developer.ninjatrader.com/docs/desktop/applyto\#examples)

```jsx-150469391 csharp
// Define the custom button control object
System.Windows.Controls.Button myButton = new System.Windows.Controls.Button
{
    Name = "myButton",
    Content = "Buy",
    Foreground = Brushes.White,
    Background = Brushes.Green,
};

// Create a custom SimpleFont object and then apply it to the button
SimpleFont myFont = new SimpleFont("Consolas", 22);

myFont.ApplyTo(myButton);

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/applyto\#definition)

Applies a custom **SimpleFont** object's properties (family, size, and style) to a [Windows Control](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control?view=windowsdesktop-9.0&redirectedfrom=MSDN).

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/applyto\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/applyto\#syntax)

`<simplefont>.ApplyTo(DependencyObject target)`

## [Parameters](https://developer.ninjatrader.com/docs/desktop/applyto\#parameters)

| Parameter | Description |
| --- | --- |
| target | The [DependencyObject](https://msdn.microsoft.com/en-us/library/system.windows.dependencyobject(v=vs.110).aspx) to apply the SimpleFont object |

## [Examples](https://developer.ninjatrader.com/docs/desktop/applyto\#examples)

```jsx-150469391 csharp
// Define the custom button control object
System.Windows.Controls.Button myButton = new System.Windows.Controls.Button
{
    Name = "myButton",
    Content = "Buy",
    Foreground = Brushes.White,
    Background = Brushes.Green,
};

// Create a custom SimpleFont object and then apply it to the button
SimpleFont myFont = new SimpleFont("Consolas", 22);

myFont.ApplyTo(myButton);

```