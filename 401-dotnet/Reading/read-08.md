# Read: Collections & Enums

- C# .0 In a Nutshell - Ch. 7 Collections(pg. 301-313, pg 324-327,)
    - If you have time to read the whole chapter – I recommend it.
- C# 7.0 in a Nutshell: Pg 118-124
- [Collections](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections)
- [Enums](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/enum)

## Collections
- Colletion Categories
    - interfaces that define standard collection protocols
    - ready-to-use collection classes (lists, dictionaries, etc)
    - Base classes for writing application-specific collections

- Collection Namespaces
    - `System.Collections` - Non generic
    - `System.Collections.Specialized` - strongly typed non-generic
    - `System.Collections.Generic` - Generic (take any type)
    - `System.Collections.ObjectModel` - Proxies and bases for custom collections    
    - `System.Collections.Concurrent` - Thread-safe collections

### Enumeration
- Give the ability to traverse the contents of the collection.
- 2 interfaces
    - `IEnumerable`
    - `IEnumerator`
- IEnumerator
``` C#
public interface IEnumerator
{
    //looks like a linkedlist method
    bool MoveNext();
    object Current { get; }
    void Reset();
}
```
- IEnumerable
    - Collections do not usually implement enumerators: instead, they provide enumerators via `IEnumerable`

- Methods rarely call on enumerators directly cause `foreach` does it for you.

- Generic
    - `IEnumbeable<T>` and `IEnumerator<T>`

## Implementing the Enumeration Interfaces
- Support the `foreach` statement
- to interoperable with anything expecting a standard collection
- To meet the requirements of a more sophisticated collection interface
- to support collection initializers

### ICollection and IList Interfaces
- Enumeration allows for forward-only iteration over a collection
    - does not provide info about the collections size
- use `ICollection` `IList` and `IDictionary`
- `IEnumerable<T>` - Provides minimum functionality (enumeration only)
- `ICollection<T>` - Provides medium functionality
- `IList<T>`/`IDictionary<K,V>` - provide maximum functionality

- `ICollection<T>`
``` C#
public interface ICollection<T> : IEnumerable<T>, IEnumerable
{
    int Count { get; }
    bool Contains (T item);
    void CopyTo (T[] array, int arrayIndex);
    bool IsReadOnly { get; }
    void Add(T item);
    bool Remove (T item);
    void Clear();
}
```


- `IList<T>`
``` C#
public interface IList<T> : ICollection<T>, IEnumerable<T>, IEnumerable
{
    T this [int index] { get; set; }
    int IndexOf (T item);
    void Insert (int index, T item);
    void RemoveAt (int index);
}
```

### LinkedList<T>
- Generic doubly linked list.
```C#
public sealed class LinkedListNode<T>
{
    public LinkedList<T> List { get; }
    public LinkedListNode<T> Next { get; }
    public LinkedListNode<T> Previous { get; }
    public T Value { get; set; }
}
```
- LinkedList<string> example
``` C#
var tune = new LinkedList<string>();
tune.AddFirst ("do"); // do
tune.AddLast ("so"); // do - so
tune.AddAfter (tune.First, "re"); // do - re- so
tune.AddAfter (tune.First.Next, "mi"); // do - re - mi- so
tune.AddBefore (tune.Last, "fa"); // do - re - mi - fa- so
tune.RemoveFirst(); // re - mi - fa - so
tune.RemoveLast(); // re - mi - fa
LinkedListNode<string> miNode = tune.Find ("mi");
tune.Remove (miNode); // re - fa
tune.AddFirst (miNode); // mi- re - fa
foreach (string s in tune) Console.WriteLine (s);
```

### Queue<T>
- (FIFO) First in first out
- Queue<int> example
```C#
var q = new Queue<int>();
q.Enqueue (10);
q.Enqueue (20);
int[] data = q.ToArray(); // Exports to an array
Console.WriteLine (q.Count); // "2"
Console.WriteLine (q.Peek()); // "10"
Console.WriteLine (q.Dequeue()); // "10"
Console.WriteLine (q.Dequeue()); // "20"
Console.WriteLine (q.Dequeue()); // throws an exception (queue empty)
```

### Stack
- (LIFO) Last in first out
- Stack<int> example
```C#
var s = new Stack<int>();
s.Push (1); // Stack = 1
s.Push (2); // Stack = 1,2
s.Push (3); // Stack = 1,2,3
Console.WriteLine (s.Count); // Prints 3
Console.WriteLine (s.Peek()); // Prints 3, Stack = 1,2,3
Console.WriteLine (s.Pop()); // Prints 3, Stack = 1,2
Console.WriteLine (s.Pop()); // Prints 2, Stack = 1
Console.WriteLine (s.Pop()); // Prints 1, Stack = <empty>
Console.WriteLine (s.Pop()); // throws exception
```

### Enums
- A value type that lets you specify a group of named numeric constans
```C#
public enum BorderSide {Left, Right, Top, Bottom}

BorderSide topSide = BorderSide.Top;
bool isTop = (topSide == BorderSide.Top);
```
- Underlying integral value.
    - Automatically assigned 0,1,2... in declaration order
    - Can be changed by dev
- Can change integral type like `byte`

### Enum Conversion
- can cast enum instance from 1 integral type to another
    - must use explicit cast

### Flag Enums
- YOu can combine enum members
``` C#
[Flags]
public enum BorderSides {None=0, Left=1, Right=2, Top=4, Bottom=4}
```
### Enum Operators
- `= == != < > <= >= + - ^ & | - += -= ++ -- sizeof`

### Type-Safety Issues
### Nested Types
- you can define/declare types within another type
```C#
public class OuterLevel
{
    public class Nested{}
    public enum Color { Red, Blue, Tan }
}
```
- nested typed features:
    - It can access the enclosing type's private members and everything else the enclosing type can access.
    - It can be declared with the full range of access modifiers, rather than just `public` and `internal`
    - The default accessibility for a nested type is `private` not `internal`.

### Generics
- inheritance vs generics
    - inheritance express reusability with a base type
    - Generics express reusability with a "template" that contains "placeholder" types.
        - generics can increase type safety
- `<T>` - is the place holder for the type
### Why Generics
- provide code to be reusable across different types.

## Collections
- 2 ways of grouping objects
    - arrays - fixed number of objects
    - collections - unknown or flexible number of objects
- can use `for` or `foreach` to iterate through a collection

### Kinds of Collections
- `System.Collections.Generic`
- `System.Collections.Concurrent`
- `System.Collections`

- Similar data can often be handled more efficiently when stored and manipulated as a collection.
- Collections can be manipulated (add, remove and modify) the [System.Array](https://docs.microsoft.com/en-us/dotnet/api/system.array?view=netframework-4.8) class or the classes in the [System.Collection](https://docs.microsoft.com/en-us/dotnet/api/system.collections?view=netframework-4.8), [system.Collection.Generic](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic?view=netframework-4.8), [System.Collections.Concurrent](https://docs.microsoft.com/en-us/dotnet/api/system.collections.concurrent?view=netframework-4.8), and/or [System.Collections.immutable](https://docs.microsoft.com/en-us/dotnet/api/system.collections.immutable?view=netcore-3.1) namespaces.
- In C# collections come in a variety of types: Generic, Non-Generic, Concurrent and Immutable
    - Generic:
        - are type-safe at compile time
        - Typically are offer better performance
        - Accept a type parameter when they are constructed
            - Items do not require casting to/from `object` type when added or removed
    - Non-Generic
        - Store items as `objects` therefore require casting.
    - Concurrent
        - provide efficient thread-safe operations
        - Allows for safe and efficient use of multi-threading.
    - Immutable
        - They are just that: immutable
        - Immutable collections are safe from changes



### Common collection features
- All collections implement (directly or indirectly) the [`ICollection`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.8) or the [`ICollection<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=netframework-4.8) interfaces.
- Common feature for all collectors:
    1. The ability to enumerate through the collection
    1. The ability to copy the collection contents to an array
        - using the `.CopyTo()` method

- Many collection classes contain the following features:
    1. Capacity and Count properties
        - The capacity is the number of elements it *can* contain                
        - The count is the number of elements it *actually* contains
    > Most collections automatically expand in capacity when the current capacity is reached. The memory is reallocated, and the elements are copied from the old collection to the new one. This reduces the code required to use the collection; however, the performance of the collection might be negatively affected. For example, for List<T>, If Count is less than Capacity, adding an item is an O(1) operation. If the capacity needs to be increased to accommodate the new element, adding an item becomes an O(n) operation, where n is Count. The best way to avoid poor performance caused by multiple reallocations is to set the initial capacity to be the estimated size of the collection.<sub>[1](https://docs.microsoft.com/en-us/dotnet/standard/collections/)</sub>
    1. Consistent lower bound
        - All indexed collections in `System.Collections` are 0-indexed
    1. Synchronization for access from multiple threads.
        - *TODO* read more into mutli-threading and `System.Collections.Concurrent`

### Choosing a Collection

I want to... | Generic option | Non-generic option 
--- | --- | ---
Store items as a key/value pair for quick loop-up by key | [`Dictionary<TKey,TValue>`](TODO) | [`Hashtable`](TODO)
Access items by index | [`List<T>`](TODO) | [`Array`](TODO) or [`ArrayList`](TODO)
First-in-first-out (FIFO) | [`Queue<T>`](TODO) | [`Queue`](TODO)
Last-in-first-out (LIFO) | [`Stack<T>`](TODO) | [`Stack`](TODO)
Access items sequentially | [`LinkedList<T>`](TODO) | None
Receive notifications when an item is removed or added to the collection | [`ObservableCollection<T>`](TODO) | None
Sorted Collection | [`SortedList<TKey,Value>`](TODO) | [`SortedList`]
Set for mathematical functions | [`HashSet<T>`](TODO) or [`SortedSet<T>`](TODO)


