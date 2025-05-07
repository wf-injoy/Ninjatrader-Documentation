Looping commands control execution flow of your script. If you wanted to print the word **NinjaTrader** 100 times, you could either use 100 lines of code or do the same using a looping command in only a few lines of code.

## [While Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#while-loop)

```jsx-150469391 csharp
while (Boolean expression)
{
     //Do something here
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
int x = 0;
while (x < 100)
{
      Print("NinjaTrader");
      x = x + 1;
}

```

## [Do While Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#do-while-loop)

```jsx-150469391 csharp
do
{
     //Do something here
}
while (Boolean expression)

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
int x = 0;
do
{
      Print("NinjaTrader");
      x = x + 1;
}
while (x < 100)

```

## [For Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#for-loop)

```jsx-150469391 csharp
for (initializer; boolean expression; iterator)
{
     //Do something here
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
for (int x = 0; x < 100; x++)
{
      Print("NinjaTrader");
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
for (int x = 0; x < 100; x++)
{
      Print("NinjaTrader");
}

```

## [Foreach Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#foreach-loop)

```jsx-150469391 csharp
foreach (type identifier in boolean expression)
{
     // Do something here
}

```

```jsx-150469391 csharp
// Count the number of oatmeal cookies in a cookie jar
int oatmealCookies = 0;
foreach (cookie in cookieJar)
{
*      if (cookie.Type == Oatmeal)
      {
          oatmealCookies = oatmealCookies + 1;
      }
}
Print("There are " + numberOatmeal.ToString() + " oatmeal cookies in the cookie jar.");

```

## [Break and Continue](https://developer.ninjatrader.com/docs/desktop/looping_commands\#break-and-continue)

You can use the **break** command to exit a loop at any time. The following example is an infinite loop, but we will break out after the first **Print** statement.

```jsx-150469391 csharp
// Exit the infinite loop after the first iteration
* while (0 == 0)
* {
      Print("NinjaTrader");
      break;
}

```

The **continue** command will jump ahead to the next iteration of the loop. The following example will never print **NinjaTrader**, because the **continue** command sends control back to the top of the loop each time.

```jsx-150469391 csharp
// Never prints "NinjaTrader"

for (int x = 0; x < 100; x++)
{
      continue;
      Print("NinjaTrader");
}

```

```jsx-150469391 csharp
// Never prints "NinjaTrader"
for (int x = 0; x < 100; x++)
{
      continue;
      Print("NinjaTrader");
}

```

Looping commands control execution flow of your script. If you wanted to print the word **NinjaTrader** 100 times, you could either use 100 lines of code or do the same using a looping command in only a few lines of code.

## [While Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#while-loop)

```jsx-150469391 csharp
while (Boolean expression)
{
     //Do something here
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
int x = 0;
while (x < 100)
{
      Print("NinjaTrader");
      x = x + 1;
}

```

## [Do While Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#do-while-loop)

```jsx-150469391 csharp
do
{
     //Do something here
}
while (Boolean expression)

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
int x = 0;
do
{
      Print("NinjaTrader");
      x = x + 1;
}
while (x < 100)

```

## [For Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#for-loop)

```jsx-150469391 csharp
for (initializer; boolean expression; iterator)
{
     //Do something here
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
for (int x = 0; x < 100; x++)
{
      Print("NinjaTrader");
}

```

```jsx-150469391 csharp
// Print NinjaTrader 100 times to the output window
for (int x = 0; x < 100; x++)
{
      Print("NinjaTrader");
}

```

## [Foreach Loop](https://developer.ninjatrader.com/docs/desktop/looping_commands\#foreach-loop)

```jsx-150469391 csharp
foreach (type identifier in boolean expression)
{
     // Do something here
}

```

```jsx-150469391 csharp
// Count the number of oatmeal cookies in a cookie jar
int oatmealCookies = 0;
foreach (cookie in cookieJar)
{
*      if (cookie.Type == Oatmeal)
      {
          oatmealCookies = oatmealCookies + 1;
      }
}
Print("There are " + numberOatmeal.ToString() + " oatmeal cookies in the cookie jar.");

```

## [Break and Continue](https://developer.ninjatrader.com/docs/desktop/looping_commands\#break-and-continue)

You can use the **break** command to exit a loop at any time. The following example is an infinite loop, but we will break out after the first **Print** statement.

```jsx-150469391 csharp
// Exit the infinite loop after the first iteration
* while (0 == 0)
* {
      Print("NinjaTrader");
      break;
}

```

The **continue** command will jump ahead to the next iteration of the loop. The following example will never print **NinjaTrader**, because the **continue** command sends control back to the top of the loop each time.

```jsx-150469391 csharp
// Never prints "NinjaTrader"

for (int x = 0; x < 100; x++)
{
      continue;
      Print("NinjaTrader");
}

```

```jsx-150469391 csharp
// Never prints "NinjaTrader"
for (int x = 0; x < 100; x++)
{
      continue;
      Print("NinjaTrader");
}

```