## [CS1513](https://developer.ninjatrader.com/docs/desktop/cs1513\#cs1513)

The following **CS1513** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

### Error Code Explanation

This error is most common with chaining if-else or loop statements.

Please check all code segments and statements are closed. Every opening curly brace '{' needs a matching closing curly brace '}'.

### Error Description \#1

} expected

#### Erroneous Sample Code - If statement is not closed

```jsx-150469391 csharp
if (CurrentBar < 1)
{
// Do something
<--- Missing closing curly brace

```

#### Resolution Sample Code - If statement is closed

```jsx-150469391 csharp
if (CurrentBar < 1)
{
// Do something
}

```

## [CS1513](https://developer.ninjatrader.com/docs/desktop/cs1513\#cs1513)

The following **CS1513** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

### Error Code Explanation

This error is most common with chaining if-else or loop statements.

Please check all code segments and statements are closed. Every opening curly brace '{' needs a matching closing curly brace '}'.

### Error Description \#1

} expected

#### Erroneous Sample Code - If statement is not closed

```jsx-150469391 csharp
if (CurrentBar < 1)
{
// Do something
<--- Missing closing curly brace

```

#### Resolution Sample Code - If statement is closed

```jsx-150469391 csharp
if (CurrentBar < 1)
{
// Do something
}

```