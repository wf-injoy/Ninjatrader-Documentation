## [Definition](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#definition)

Returns the painted width of the chart bar. The **GetBarPaintWidth()** method will return a minimum value of 1.

## Note

This is an [abstract](https://msdn.microsoft.com/en-us/library/sf985hc5.aspx) method which is required to compile a ChartStyle object. If you do not plan on recalculating a barWidth, simply return the default barWidth parameter which is passed in this method. Please see the Examples section of this page for more information.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#method-return-value)

An **int** value

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#syntax)

You must override this method using the following syntax:

`public override int GetBarPaintWidth(int barWidth) { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#method-parameters)

| Parameter | Description |
| --- | --- |
| **barWidth** | An **int** value representing the current width of the bar to calculate |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#examples)

### Returning the default barWidth

```jsx-150469391 csharp

public override int GetBarPaintWidth(int barWidth)
{
    return barWidth
}

```

### Calculating and returning a new barWidth from the original barWidth

```jsx-150469391 csharp
public override int GetBarPaintWidth(int barWidth)
{
    // calculate a new bar width
    return 1 + 2 * (barWidth - 1) + 2 * (int) Math.Round(Stroke.Width);
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#definition)

Returns the painted width of the chart bar. The **GetBarPaintWidth()** method will return a minimum value of 1.

## Note

This is an [abstract](https://msdn.microsoft.com/en-us/library/sf985hc5.aspx) method which is required to compile a ChartStyle object. If you do not plan on recalculating a barWidth, simply return the default barWidth parameter which is passed in this method. Please see the Examples section of this page for more information.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#method-return-value)

An **int** value

## [Syntax](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#syntax)

You must override this method using the following syntax:

`public override int GetBarPaintWidth(int barWidth) { }`

## [Method Parameters](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#method-parameters)

| Parameter | Description |
| --- | --- |
| **barWidth** | An **int** value representing the current width of the bar to calculate |

## [Examples](https://developer.ninjatrader.com/docs/desktop/getbarpaintwidth\#examples)

### Returning the default barWidth

```jsx-150469391 csharp

public override int GetBarPaintWidth(int barWidth)
{
    return barWidth
}

```

### Calculating and returning a new barWidth from the original barWidth

```jsx-150469391 csharp
public override int GetBarPaintWidth(int barWidth)
{
    // calculate a new bar width
    return 1 + 2 * (barWidth - 1) + 2 * (int) Math.Round(Stroke.Width);
}

```