# Read: LINQ & Delegates

- [LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)
- [Introduction To LINQ Queries](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
- [Basic LINQ Query Operators](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/basic-linq-query-operations)
- [Walkthrough Writing LINQ Queries in C#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq)
- C# 7.0 In a Nutshell - Chapter 8: LINQ Queries

## Language Integrated Query (LINQ)
- Traditionally, queries against data are expressed as simple string without type checking at compilt time. 
- LINQ provides a consistent query experience for
    - objects (LINQ to Objects)
    - relational databases (LINQ to SQL)
    - XML (LINQ to XML)
- supports IEnumerable
``` C#
// LINQ example
class LINQQueryExpressions
{
    static void Main()
    {

        // Specify the data source.
        int[] scores = new int[] { 97, 92, 81, 60 };

        // Define the query expression.
        IEnumerable<int> scoreQuery =
            from score in scores
            where score > 80
            select score;

        // Execute the query.
        foreach (int i in scoreQuery)
        {
            Console.Write(i + " ");
        }
    }
}
// Output: 97 92 81
```
### Query Expression overview
- can be used to query and to transform data from any LINQ-enabled data source.
- Query expressions are familiar C# constructs
- Variables are strongly typed
- query is not executed until you iterate over the query variable
- At compile time, qe are converted to Standard Query Operator method calls. 
- Its recommended that you use query syntax when writing LINQ queries.
    - query expressions are often more readable.

### Intro to LINQ Queries
- A query is an expression that retrieves data from a data source. 
- 3 Parts of a Query Operation
    1. Obtain the data source
    1. Create the query
    1. Execute the query
``` C#
class IntroToLINQ
{
    static void Main()
    {
        // The Three Parts of a LINQ Query:
        // 1. Data source.
        int[] numbers = new int[7] { 0, 1, 2, 3, 4, 5, 6 };

        // 2. Query creation.
        // numQuery is an IEnumerable<int>
        var numQuery =
            from num in numbers
            where (num % 2) == 0
            select num;

        // 3. Query execution.
        foreach (int num in numQuery)
        {
            Console.Write("{0,1} ", num);
        }
    }
}
```
### The Data Source
- Example was an array
``` C#
// LINQ to XML
XElement contacts = XElement.Load(@"c:\myContactsList.xml");
// LINQ to SQL
// Need to create an object-relational mapping at design time. (manually or using VS LINQ to SQL tools)
Northwnd db = new Northwnd(@"c:\northwnd.mdf");

IQueryable<Customer> custQuery = 
    from cust in db.Customers
    where cust.City == "London"
    select cust;
```

### The Query
- The query specifies what information to retrieve from the data source(s).
    - Can specify how the information should be sorted, grouped, and shaped.

### The Execution
- Deferred Execution
    - the actual execution of the query is deferred until it is iterated over. 
    - Because the query variable itself never hold the query results, you can execute it as often as you like. 
- Forcing Immediate Execution
    - Queries that perform aggregation functions over a range of source elements must first iterate over those elements. 
        - `Count Max Average` and `First`
    - to force immediate execution of a query use `ToList` or `ToArray` methods.

## Basic LINQ Query Operations
- Obtaining a Data Source
- Filtering
- Ordering
- Grouping
- Joining
- Selecting 
