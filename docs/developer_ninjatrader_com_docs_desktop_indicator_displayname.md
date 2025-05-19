## [Definition](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#definition)

Determines the text display on the chart panel. This is also listed in the UI as the "Label" which can be manually changed (if not overridden). The default behavior of this property will include the NinjaScript type Name along with its input and data series parameters. However this behavior can be overridden if desired.

## Note

For modifying the string which is used in the list of available indicators, please see the [Name](https://developer.ninjatrader.com/docs/desktop/name) property.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#property-value)

A virtual string. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#syntax)

`DisplayName`

You may choose to override this property using the following syntax:

```jsx-150469391 csharp
public override string DisplayName
{
  get { }
}

```

## [Examples](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#examples)

### Printing the default DisplayName which displays on the chart label

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Example Indicator";
  }
}

protected override void OnBarUpdate()
{
  Print(DisplayName);   //Output:  Example Indicator(ES 03-15 (1 Minute))
}

```

### Overriding the DisplayName to customize the chart label

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Example Indicator";
  }
}

public override string DisplayName
{
  get { return "My Custom Display " + Name; }
}

protected override void OnBarUpdate()
{
  Print(DisplayName);   //Output:  My Custom Display Example Indicator
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#definition)

Determines the text display on the chart panel. This is also listed in the UI as the "Label" which can be manually changed (if not overridden). The default behavior of this property will include the NinjaScript type Name along with its input and data series parameters. However this behavior can be overridden if desired.

## Note

For modifying the string which is used in the list of available indicators, please see the [Name](https://developer.ninjatrader.com/docs/desktop/name) property.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#property-value)

A virtual string. This property is read-only.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#syntax)

`DisplayName`

You may choose to override this property using the following syntax:

```jsx-150469391 csharp
public override string DisplayName
{
  get { }
}

```

## [Examples](https://developer.ninjatrader.com/docs/desktop/indicator_displayname\#examples)

### Printing the default DisplayName which displays on the chart label

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Example Indicator";
  }
}

protected override void OnBarUpdate()
{
  Print(DisplayName);   //Output:  Example Indicator(ES 03-15 (1 Minute))
}

```

### Overriding the DisplayName to customize the chart label

```jsx-150469391 csharp
protected override void OnStateChange()
{
  if (State == State.SetDefaults)
  {
    Name = "Example Indicator";
  }
}

public override string DisplayName
{
  get { return "My Custom Display " + Name; }
}

protected override void OnBarUpdate()
{
  Print(DisplayName);   //Output:  My Custom Display Example Indicator
}

```