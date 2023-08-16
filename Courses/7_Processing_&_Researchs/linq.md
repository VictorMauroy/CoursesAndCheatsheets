# <span style="color: green"><u>**LINQ**</u></span>



## **What is LINQ ?**

**Linq** for **L**anguage **In**tegrated **Q**uery. As its name says, that's an integrated language that helps doing requests on
collections of data.

Linq uses a vocabulary similar to SQL and you'll find many words in common, such as `select`, `from`, `where`, etc. Making it really interesting if you have some basics knowledge of database development.

<div style="display: flex;">
    <div style="flex: 45%; padding: 5px;">
        <img src="../_resources/linq-query-complete-operation.png" alt="Dungeon power" />
    </div>
    <div style="flex: 45%; padding: 5px;">
        <p>
        Here is a scheme from Microsoft Learn that explains how Linq query works.
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

First, we need datas on which we can execute our query, let's define a collection of objects.
<br>
**What is a collection ?** For instance, it can be a list, an array or an Enumerable/IEnumerable.

```csharp
int[] numbers = new int[5] {15, 16, 2, 55, -15};

//You can also use custom objects, it's mainly used with entities (from Entity Framework)
List<Cat> cats = new List<Cat>();
```

