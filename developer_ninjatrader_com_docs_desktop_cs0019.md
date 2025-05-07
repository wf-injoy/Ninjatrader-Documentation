The following CS0019 error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0019\#error-code-explanation)

Strings cannot be compared with relational operators (<, >, <=, >=, ==, !=) to other object types. Strings can only be compared to other strings and only through the use of equality operators (==, !=).

### Error Description \#1

Operator '==' cannot be applied to operands of type 'string' and 'int'

```jsx-150469391 csharp
// Erroneous Sample Code – Cannot compare a string to an integer
if ("string" == 5)

```

```jsx-150469391 csharp
// Resolution Sample Code – Compare a string with another string
if ("string" == intValue.ToString());

```

### Error Description \#2

Operator ‘<’ cannot be applied to operands of type ‘string’ and ‘double’

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot compare a string to a double
if ("string" >= 1.2)

```

```jsx-150469391 csharp
// Resolution Sample Code - Testing to see if the strings are not the same
if ("string" != "string2")

```

### Error Description \#3

Operator ‘>’ cannot be applied to operands of type ‘string’ and ‘string’

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot quantitatively compare a string to another string
if ("string" > "string2")

```

```jsx-150469391 csharp
// Resolution Sample Code - Testing to see if both strings are the same
if ("string" == "string2")

```

### Additional Error Descriptions

- Operator ‘<’ cannot be applied to operands of type ‘string’ and ‘string’
- Operator ‘<=’ cannot be applied to operands of type ‘string’ and ‘string’
- Operator ‘>=’ cannot be applied to operands of type ‘string’ and ‘string’

The following CS0019 error code information is provided within the context of **NinjaScript**. The examples provided are only a subset of potential problems that this error code may reflect. In any case, the examples below provide a reference of coding flaw possibilities.

## [Error Code Explanation](https://developer.ninjatrader.com/docs/desktop/cs0019\#error-code-explanation)

Strings cannot be compared with relational operators (<, >, <=, >=, ==, !=) to other object types. Strings can only be compared to other strings and only through the use of equality operators (==, !=).

### Error Description \#1

Operator '==' cannot be applied to operands of type 'string' and 'int'

```jsx-150469391 csharp
// Erroneous Sample Code – Cannot compare a string to an integer
if ("string" == 5)

```

```jsx-150469391 csharp
// Resolution Sample Code – Compare a string with another string
if ("string" == intValue.ToString());

```

### Error Description \#2

Operator ‘<’ cannot be applied to operands of type ‘string’ and ‘double’

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot compare a string to a double
if ("string" >= 1.2)

```

```jsx-150469391 csharp
// Resolution Sample Code - Testing to see if the strings are not the same
if ("string" != "string2")

```

### Error Description \#3

Operator ‘>’ cannot be applied to operands of type ‘string’ and ‘string’

```jsx-150469391 csharp
// Erroneous Sample Code - Cannot quantitatively compare a string to another string
if ("string" > "string2")

```

```jsx-150469391 csharp
// Resolution Sample Code - Testing to see if both strings are the same
if ("string" == "string2")

```

### Additional Error Descriptions

- Operator ‘<’ cannot be applied to operands of type ‘string’ and ‘string’
- Operator ‘<=’ cannot be applied to operands of type ‘string’ and ‘string’
- Operator ‘>=’ cannot be applied to operands of type ‘string’ and ‘string’