The following **CS0103** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0103\#error-code-explanation)

When a variable is used before declaration, the compiler will not know what it is. This error is also commonly invoked by typos.

Please ensure that you have declared your variables prior to using them. If variables are declared or properties already exist, please check for typos.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0103\#error-description-\#1)

The name ' **identifier**' does not exist in the current context

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0103\#examples)

### Example \#1

```jsx-150469391 csharp
// Erroneous Sample Code - 'CurentBar' does not exist since it has been spelled incorrectly (missing an 'r')
if (CurentBar < 10)

```

**Resolution Sample Code** \- ' **CurrentBar**' exists since it is spelled correctly

```jsx-1168641291 csharp
if (CurrentBar < 10)

```

### Example \#2

```jsx-150469391 csharp
// Erroneous Sample Code - 'newVariable' is not declared
newVariable = 10;

```

**Resolution Sample Code** \- ' **newVariable**' is now declared as an integer

```jsx-1168641291 csharp
int newVariable = 10;

```

The following **CS0103** error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0103\#error-code-explanation)

When a variable is used before declaration, the compiler will not know what it is. This error is also commonly invoked by typos.

Please ensure that you have declared your variables prior to using them. If variables are declared or properties already exist, please check for typos.

## [Error Description \#1](https://developer.ninjatrader.com/docs/desktop/cs0103\#error-description-\#1)

The name ' **identifier**' does not exist in the current context

## [Examples](https://developer.ninjatrader.com/docs/desktop/cs0103\#examples)

### Example \#1

```jsx-150469391 csharp
// Erroneous Sample Code - 'CurentBar' does not exist since it has been spelled incorrectly (missing an 'r')
if (CurentBar < 10)

```

**Resolution Sample Code** \- ' **CurrentBar**' exists since it is spelled correctly

```jsx-1168641291 csharp
if (CurrentBar < 10)

```

### Example \#2

```jsx-150469391 csharp
// Erroneous Sample Code - 'newVariable' is not declared
newVariable = 10;

```

**Resolution Sample Code** \- ' **newVariable**' is now declared as an integer

```jsx-1168641291 csharp
int newVariable = 10;

```