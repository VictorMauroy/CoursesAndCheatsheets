# <span style="color: green"><u>**Dictionaries**</u></span>

Dictionaries are interesting to save values in a different way than arrays or lists. <br>
It allows to save a **value** for a special **key** index. <br>
Where the key can be anything, usually a string or an int and the value can also be a string, int or an array, a list, etc.

Require : `using System.Collections.Generic;`





## **Creating a new dictionary**

```csharp
IDictionary<int, int> numberOccurence = new Dictionary<int, int>(); 
// One integer and its occurence count 
```

```csharp
IDictionary<string, string[]> citiesPeoples = new Dictionary<string, string[]>(); 
// One city name for many people names
```





## **Adding and updating values**

```csharp
myDictionary.Add("txt", "notepad.exe");
```

```csharp
myDictionary["txt"] = "notepad.exe";
```





## **Checking key or values**
```csharp
if(myDictionary.TryGetValue("txt", out theValue)) {}
```

```csharp
if(myDictionary.ContainsKey("txt")) {}
```
```csharp
if(myDictionary.ContainsValue("notepad.exe")) {}
```





## **Iteration on dictionaries**
Require : using System.Linq; to use ElementAt(index)
```csharp
for(int i =0; i < numberOccurence.Count; i++) 
{
    if(numberOccurence.ElementAt(i).Value % 2 != 0) 
        return numberOccurence.ElementAt(i).Key;
}
```
```csharp
foreach( KeyValuePair<string, string> kvp in openWith )
{
    Console.WriteLine(
        "Key = {0}, Value = {1}",
        kvp.Key, kvp.Value
    );
}
```




<details>
<summary>Acces keys or values distinctly </summary>
<br>

An exemple with a simple dictionary : 
```csharp
Dictionary<string, string> openWith =
    new Dictionary<string, string>();
```

**Iterating on the values (only)**

```csharp
Dictionary<string, string>.ValueCollection valueColl =
    openWith.Values;

// The elements of the ValueCollection are strongly typed
// with the type that was specified for dictionary values.
Console.WriteLine();
foreach( string s in valueColl )
{
    Console.WriteLine("Value = {0}", s);
}
```
<br>

**Iterating on the keys (only)**

```csharp
// To get the keys alone, use the Keys property.
Dictionary<string, string>.KeyCollection keyColl =
    openWith.Keys;

// The elements of the KeyCollection are strongly typed
// with the type that was specified for dictionary keys.
Console.WriteLine();
foreach( string s in keyColl )
{
    Console.WriteLine("Key = {0}", s);
}
```

</details>