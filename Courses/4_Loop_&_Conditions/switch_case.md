# <span style="color: green"><u>**Switch expressions**</u></span>



## **Traditionnal switch case**

**Switch usefulness:** The switch case expression allows to do specific actions depending of a given value. In some case, it could be a good idea to replace an `if{} else if{} else{}` by a switch case.

Note that the traditionnal switch case can only work with `integer`, `enum`, `char` and `string`.

```csharp
enum Behavior {
    Agressive,
    Passive
}

Behavior enemyBehavior = Behavior.Agressive;

switch(enemyBehavior)
{
    case Behavior.Agressive:
        // Do something
        break;
    
    case Behavior.Passive:
        // Do something else
        break;
    
    default:
        //Do something when it did not matched any cases
        break;
}
```
`switch` => depending of (your value). <br>
`case` => in case your value is equal to (a value). <br>
`default` => default action if it didn't matched any case.





## **Enhanced switch expression**
Introduced in C# 8.0. That switch expression is an enhancement over the traditional switch statement, which can only be used to evaluate `integer, string, enum or char`.
```csharp
int number = 2;
string result = number switch
{
    1 => "One",
    2 => "Two",
    3 => "Three",
    _ => "Other"
};
```
The above expression will return a different string depending of the number we gave it. Currently, it will return "Two" because we gave it an integer with the value 2. 

It can be used to **switftly return a result for a function** :
```csharp
public static string GetStringValue(int number) => c switch
{
    15 => "Quinze",
    29 => "Vingt-neuf",
    _ => "Other"
};
```

```csharp
public static string GetDataStatus(int data)
{
    return data switch
    {
        int value when value > 0 && value <= 100 => "Valid data",
        int value when value > 100 => "Out of range",
        int value when value <= 0 => "Invalid data",
        _ => "Unknown data"
    };
}
```
`when` is a keyword that can be used when doing specific operations, like returning a new variable that is yet to be set. <br>
Note: In the last function, which uses the `when` keyword, we define an `int value`. `value` will automaticaly store the value of the switch parameter `data` and we will be also to do checks and operations on it.
