# <span style="color: green"><u>**Manage errors**</u></span>
Explainations: https://www.w3schools.com/cs/cs_exceptions.php





## **Try Catch**
The `try` statement allows you to define a block of code to be tested for errors while it is being executed.

The `catch` statement allows you to define a block of code to be executed, if an error occurs in the try block.

```csharp
try
{
  int[] myNumbers = {1, 2, 3};
  Console.WriteLine(myNumbers[10]);
}
catch (Exception e)
{
  Console.WriteLine("Something went wrong.");
}
```

Exception manipulation: By saving the exception in `e`, you can execute and manipulate some functionnalities around the exception. For instance a `Console.WriteLine(e.Message);` will return the predifined error message.

**Work with specific exceptions:**
It is also possible to threat specific exceptions by defining their name in the catch statement.
```csharp
try {
    // Something
} 
catch(NullReferenceException) {
    // Do something in case we encounter the NullReferenceException 
} 
catch (Exception) {
    //Do something for all the other exceptions
}
```





## **Try Catch Finally**
The `finally` statement lets you execute code, after try...catch, regardless of the result.

```csharp
try
{
  int[] myNumbers = {1, 2, 3};
  Console.WriteLine(myNumbers[10]);
}
catch (Exception e)
{
  Console.WriteLine("Something went wrong.");
}
finally
{
  Console.WriteLine("The 'try catch' is finished.");
}
```





## **Throw**
The `throw` statement allows you to create a custom error.<br>
The `throw` statement is used together with an **exception class**. There are many exception classes available in C#: `ArithmeticException, FileNotFoundException, IndexOutOfRangeException, TimeOutException`, etc

```csharp
if (age < 18)
{
    throw new ArithmeticException("Access denied - You must be at least 18 years old.");
}
else
{
    Console.WriteLine("Access granted - You are old enough!");
}
```