## [Definition](https://developer.ninjatrader.com/docs/desktop/entryhandling\#definition)

Sets the manner in how entry orders will handle.

## Note

This property ONLY applies to Managed order methods. When **IsUnmanaged** is set to true, Entry Handling properties will be hidden from the UI.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/entryhandling\#property-value)

An enum which sets how the entry orders are handled. Default value is **EntryHandling.AllEntries**. Possible values include:

| **EntryHandling.AllEntries** | NinjaScript will process all [order entry methods](https://developer.ninjatrader.com/docs/desktop/order_methods) until the maximum allowable entries set by the [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection) property is reached while in an open position |
| **EntryHandling.UniqueEntries** | NinjaScript will process order entry methods until the maximum allowable entries set by the EntriesPerDirection property per each uniquely named entry |

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/entryhandling\#syntax)

`EntryHandling`

## [Examples](https://developer.ninjatrader.com/docs/desktop/entryhandling\#examples)

### Allow a maximum of two entries while a position is open

```jsx-150469391 csharp
// Example #1
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         EntriesPerDirection = 2;
         EntryHandling = EntryHandling.AllEntries;
     }
}

protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1)
         EnterLong("SMA Cross Entry");
}

// EnterLong() will be processed once for each uniquely named entry.

```

### Allow a maximum of one entry per uniquely named entry

```jsx-150469391 csharp
// Example #2
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         EntriesPerDirection = 1;
         EntryHandling = EntryHandling.UniqueEntries;
     }
}

protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1)
         EnterLong("SMA Cross Entry");

    if (CrossAbove(RSI(14, 3), 30, 1)
         EnterLong("RSI Cross Entry");
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/entryhandling\#definition)

Sets the manner in how entry orders will handle.

## Note

This property ONLY applies to Managed order methods. When **IsUnmanaged** is set to true, Entry Handling properties will be hidden from the UI.

## [Property Value](https://developer.ninjatrader.com/docs/desktop/entryhandling\#property-value)

An enum which sets how the entry orders are handled. Default value is **EntryHandling.AllEntries**. Possible values include:

| **EntryHandling.AllEntries** | NinjaScript will process all [order entry methods](https://developer.ninjatrader.com/docs/desktop/order_methods) until the maximum allowable entries set by the [EntriesPerDirection](https://developer.ninjatrader.com/docs/desktop/entriesperdirection) property is reached while in an open position |
| **EntryHandling.UniqueEntries** | NinjaScript will process order entry methods until the maximum allowable entries set by the EntriesPerDirection property per each uniquely named entry |

## Warning

This property should ONLY be set from the **OnStateChange()** method during State.SetDefaults or State.Configure.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/entryhandling\#syntax)

`EntryHandling`

## [Examples](https://developer.ninjatrader.com/docs/desktop/entryhandling\#examples)

### Allow a maximum of two entries while a position is open

```jsx-150469391 csharp
// Example #1
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         EntriesPerDirection = 2;
         EntryHandling = EntryHandling.AllEntries;
     }
}

protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1)
         EnterLong("SMA Cross Entry");
}

// EnterLong() will be processed once for each uniquely named entry.

```

### Allow a maximum of one entry per uniquely named entry

```jsx-150469391 csharp
// Example #2
protected override void OnStateChange()
{
     if (State == State.SetDefaults)
     {
         EntriesPerDirection = 1;
         EntryHandling = EntryHandling.UniqueEntries;
     }
}

protected override void OnBarUpdate()
{
     if (CrossAbove(SMA(10), SMA(20), 1)
         EnterLong("SMA Cross Entry");

    if (CrossAbove(RSI(14, 3), 30, 1)
         EnterLong("RSI Cross Entry");
}

```