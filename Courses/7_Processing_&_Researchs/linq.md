# <span style="color: green"><u>**LINQ**</u></span>



## **What is LINQ ?**

**Linq** for **L**anguage **In**tegrated **Q**uery. As its name says, that's an integrated language that helps doing requests on
collections of data.

Linq uses a vocabulary similar to SQL and you'll find many words in common, such as `select`, `from`, `where`, etc. Making it really interesting if you have some basics knowledge of database development.

<div style="display: flex;">
    <div style="flex: 45%; padding: 5px;">
        <img src="resources/linq-query-complete-operation.png" alt="Dungeon power" />
    </div>
    <div style="flex: 45%; padding: 5px;">
        <p>
        Here is a scheme from Microsoft Learn that explains how Linq works.
        <br>
        <br>
        It takes a data source, such as a collection and by using a query made by Linq, you will filter it and only select the datas interesting for you. 
        <br>
        Then with a foreach loop, you can iterate on the result and make specific actions on the filtered elements.
        </p>        
    </div>
</div>





## **Where to use it ?**

**Linq** is used to query many types of content :
* **Object collections** => Linq to Objects
* **ADO.NET DataSet** => Linq to DataSet
* **XML Documents** => Linq to XML
* **Entity Framework** => Linq to Entities
* **SQL Databases** => Linq to SQL

It can also by used on **other types of datas** by implementing the interface `IQueryAble`.





## **How to use it ?**

### Define a collection of objects.
First, we need datas on which we can execute our query, let's define a collection of objects.
<br>
**What is a collection ?** For instance, it can be a list, an array or an Enumerable/IEnumerable.

```csharp
int[] numbers = new int[6] {15, -76, 16, 2, 55, -15};

//You can also use custom objects, it's mainly used with entities (from Entity Framework)
List<Cat> cats = new List<Cat>();
```


### Execute a Linq Query
Then, it is already possible to write our query. 
<br> 
Before anything, you must know that **the return type of a Linq query can change or be ambiguous**, depending of the query you write and the datas you works with.

Usually, if you work with simple types (`int`, `string`, etc.) you can easily determine what you'll return. It can be the same with complexe objects or entities if you are certain about what you want. 

Here is a basic example with a simple data types:
```csharp
IEnumerable<int> positiveNumbers = 
    from int num in numbers
    where num >= 0
    select num;
// Result : positiveNumbers 15, 16, 2, 55
```
The `from` keyword is the line where you indicate **from which collection** you want to filter datas. <br>
The `where` keyword is the **filter condition**. Only objects or variables that respect it will be taken. <br>
The `select` keyword **indicate the format** of the datas and which datas you'll return.

Linq queries return an `IEnumerable` which is a collection type of datas based on the data returned by the select. It's kinda the same as a list be you can't use the same methods. 
<br>What's good with IEnumerable is the fact that you can you call advanced methods such as the ["Criteria Linq"](criteria_linq.md) ones (ex: `Enumerable.Where()` or `Enumerable.Select()`).

<br>

**Why should you use the `var` keyword ?**
When querying a database or entities, its safer to write the expected type as `var` because it can greatly vary depending of you Linq query.
```csharp
var whiteCats = 
    from Cat cat in Cats
    where cat.furColor == "white"
    select cat;
```
Why didn't we write `IEnumerable<Cat> whiteCats` ? In the above case, it's precisely what we get so we could have done it. But look at that second example:
```csharp
var animalNamesFromThere =
    from Cat cat in Cats
    where cat.City == "Here" || cat.City == "There"
    select new { Name = cat.name, City = cat.City };
```
What are you supposed to receive ? Not a `Cat` neither a string. That's a new object that you cannot describe because it doesn't exist anywhere. So `var` became the only option.

### Iterate on the result

### Advanced Linq queries