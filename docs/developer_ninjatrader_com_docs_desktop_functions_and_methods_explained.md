Methods (called "Functions" in some other programming languages) are used to encapsulate a set of statements. They are given a name and optionally a set of input parameters. They can be "called" from any point in your NinjaScript code. Once written, we need only be concerned with what a method does. A method can return a value of any type, or return nothing.

## [Declaring a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#declaring-a-method)

A method must first be declared before you can use it in your script:

`[Access Modifier] [Return Type] [Name] (Optional parameters)`

|  |  |
| --- | --- |
| Access Modifier | Sets the access level to the method. In developing NinjaScript objects, you will likely use the private access modifier more often than any other. |
| Return Type | Sets the value type that the method will return. If it returns nothing, you will set the return type to void. |
| Name | A user defined name for the method |
| Optional Parameters | Any optional parameters that you may want to pass into the method |

## [Method With No Return Type](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#method-with-no-return-type)

```jsx-150469391 csharp
// This method prints out the data and time
private void PrintDateTime()
{
     Print(DateTime.Now.ToString());
}

```

The above method has no return type, so we use the void access modifier. We provide a user defined method name "PrintDateTime," and since there are no parameters, we complete the declaration with an "()". The method code itself is then enclosed within curly braces.

## [Method With a Return Type](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#method-with-a-return-type)

```jsx-150469391 csharp
// This method performs a calculation and returns a double value
private double Multiply(double input)
{
     return input * 10;
}

```

The above method returns a value of type double, so we use the keyword double. We provide a user defined method name "Multiply," and we declare that this method takes a parameter named "input" which is of type double. Since this method returns a value, we use the return keyword to return the value of (input \* 10) back to the calling routine.

## [Calling a Method within a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#calling-a-method-within-a-method)

```jsx-150469391 csharp
// This method performs a calculation and returns a double value
private double Multiply(double input)
{
     PrintDateTime();
     return input * 10;
}

```

Building on our examples from above, we added a call to the PrintDateTime() method within our Multiply method.

### When to use Methods

Using methods is a great way to logically organize blocks of code. If you find that you are performing the same calculations in different parts of your script, it also makes sense to encapsulate the repetitive code into a method.

For example:

Lets say you had a script that needed to calculate the average range of the past three bars in multiple locations. This is where encapsulating the logic that calculates the range into one method would be more efficient than performing the same calculation in each location.

First we declare our method using a return type of double and name it "AverageRange." There is no requirement to pass in any parameters. We then write a statement that calculates and returns the average range of the past three bars. We end up with the method below:

```jsx-150469391 csharp
// Calculates the average range of the past three bars
private double AverageRange()
{
    return ((High[1] - Low[1]) + (High[2] - Low[2]) + (High[3] - Low[3])) / 3 ;
}

```

We can then reference the AverageRange method anywhere else in our script, like in the example below:

```jsx-150469391 csharp
// Example method that calls the AverageRange() method twice
private void ExampleMethod()
{
     if (High[0] - Low[0] &gt; AverageRange())
     {
         Print("The current bar range is greater than the 3 bar average range of " +
           AverageRange().ToString());
     }
}

```

## [Declaring Variables within a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#declaring-variables-within-a-method)

You can declare variables within a method. These variables are local in scope, which means they can only be accessed within the method and not outside of it, such as in your main script.

```jsx-150469391 csharp
// Example method using a variable
private double MyMethod()
{
     double myDouble = 100.25
     return myDouble * 10;
}

```

Methods (called "Functions" in some other programming languages) are used to encapsulate a set of statements. They are given a name and optionally a set of input parameters. They can be "called" from any point in your NinjaScript code. Once written, we need only be concerned with what a method does. A method can return a value of any type, or return nothing.

## [Declaring a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#declaring-a-method)

A method must first be declared before you can use it in your script:

`[Access Modifier] [Return Type] [Name] (Optional parameters)`

|  |  |
| --- | --- |
| Access Modifier | Sets the access level to the method. In developing NinjaScript objects, you will likely use the private access modifier more often than any other. |
| Return Type | Sets the value type that the method will return. If it returns nothing, you will set the return type to void. |
| Name | A user defined name for the method |
| Optional Parameters | Any optional parameters that you may want to pass into the method |

## [Method With No Return Type](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#method-with-no-return-type)

```jsx-150469391 csharp
// This method prints out the data and time
private void PrintDateTime()
{
     Print(DateTime.Now.ToString());
}

```

The above method has no return type, so we use the void access modifier. We provide a user defined method name "PrintDateTime," and since there are no parameters, we complete the declaration with an "()". The method code itself is then enclosed within curly braces.

## [Method With a Return Type](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#method-with-a-return-type)

```jsx-150469391 csharp
// This method performs a calculation and returns a double value
private double Multiply(double input)
{
     return input * 10;
}

```

The above method returns a value of type double, so we use the keyword double. We provide a user defined method name "Multiply," and we declare that this method takes a parameter named "input" which is of type double. Since this method returns a value, we use the return keyword to return the value of (input \* 10) back to the calling routine.

## [Calling a Method within a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#calling-a-method-within-a-method)

```jsx-150469391 csharp
// This method performs a calculation and returns a double value
private double Multiply(double input)
{
     PrintDateTime();
     return input * 10;
}

```

Building on our examples from above, we added a call to the PrintDateTime() method within our Multiply method.

### When to use Methods

Using methods is a great way to logically organize blocks of code. If you find that you are performing the same calculations in different parts of your script, it also makes sense to encapsulate the repetitive code into a method.

For example:

Lets say you had a script that needed to calculate the average range of the past three bars in multiple locations. This is where encapsulating the logic that calculates the range into one method would be more efficient than performing the same calculation in each location.

First we declare our method using a return type of double and name it "AverageRange." There is no requirement to pass in any parameters. We then write a statement that calculates and returns the average range of the past three bars. We end up with the method below:

```jsx-150469391 csharp
// Calculates the average range of the past three bars
private double AverageRange()
{
    return ((High[1] - Low[1]) + (High[2] - Low[2]) + (High[3] - Low[3])) / 3 ;
}

```

We can then reference the AverageRange method anywhere else in our script, like in the example below:

```jsx-150469391 csharp
// Example method that calls the AverageRange() method twice
private void ExampleMethod()
{
     if (High[0] - Low[0] &gt; AverageRange())
     {
         Print("The current bar range is greater than the 3 bar average range of " +
           AverageRange().ToString());
     }
}

```

## [Declaring Variables within a Method](https://developer.ninjatrader.com/docs/desktop/functions_and_methods_explained\#declaring-variables-within-a-method)

You can declare variables within a method. These variables are local in scope, which means they can only be accessed within the method and not outside of it, such as in your main script.

```jsx-150469391 csharp
// Example method using a variable
private double MyMethod()
{
     double myDouble = 100.25
     return myDouble * 10;
}

```