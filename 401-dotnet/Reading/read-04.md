# Read-04 Read: Classes & Objects

- [Classes](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/classes)
- [Constructors](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors)
- [Properties](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties)
- [Stack and Heap](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties)
- [Garbage Collection Fundamentals](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals)
- C# in a Nutshell - Chapter 3

## Classes
- A class is a reference type
- Lives in the heap
- Needs to be instantiated (unless static)
### Declaring classes
`public class Customer {...}`
- class is the blueprint
- object is the thing made from the blueprint
    - `Customer obj = new Customer();`
```C#
Customer object1 = new Customer();
Customer object2 = object1;
// The 2nd one is a reference to the first one
```
### Inheritance
``` C#
public class Manager : Employee
{
    // Employee is the parent
    // Manager inherits form the employee
}
```
- C# only allows for single inheritance
    - can chain inheritance tho
- an `abstract` class is a class that is never implemented directly.

## Constructors
- they allow us to set default values
### Parameterless Constructor
- If you don't provide a constructor 
### Syntax
- declare a constructor by building a method with the same name as the class
```C#
public class Person
{
    string last;
    string first;

    public Person(string lastName, string firstName)
    {
        last = lastName;
        first = firstName;
    }
}
```
### static constructors
- will initialize static members of the type
- Static constructors are parameterless
```C#
public class Adult : Person
{
    private static int minimumAge;
    public Adult(string lastName, string firstName) : base(lastName, firstName)
    {...}

    static Adult()
    {
        minimumAge = 18;
    }
}
```

---

## Properties
- Properties allows for public access for getting and setting values while hiding implementation or verification code.
- get to get, set to set
- Properties can be `read-write`, `read-only`, or `write-only`

---

## Heap vs Stack
- 2 places where .NET stores items in memory
    - Heap and stack
### Whats the difference
- Stack: responsible for keeping track of what's executing in our code.
    - Self-maintaining: takes care of its own memory management
- Heap: Keeps track of our objects.
    - Needs garbage collection to keep clean

### Reference Types
- always goes on the Heap
### Value types
- goes where they are declared.
- If a value type is declared outside of a method but inside of a reference type it will be placed within the refereence type on the heap.
### Pointers
- a chunk of space in memory that points to another pace in memory
- can bridge the gap between stack and heap

### Garbage Collection 
- When a program reaches a certain memory threshold and we need more Heap space the GC wil kick in.
- The GC will stop all threads and fid all objects in the Heap that are not being accessed by the main program and delete them. 

---

## Fundamentals of garbage collection
- the GC is an automatic memory manager.
- prevent memory leak caused by forgetting to free an object. 
### Benefits
- Devs don't have to manually release memory.
- Allocates object on the heap efficiently
- Reclaims objects that are no longer being used and frees their memory.
- provides memory safety
### Fundamentals of memory
- Each process has its own separate virtual space.
- each process has a 2-GB virtual address space
- a dev only has to work with in the virtual address space and never manipulate physical memory.
- Virtual memory has 3 states
    - free: has no references
    - reserved: block is available for use
    - committed: block is assigned to physical storage
- virtual space can get fragmented.
- you can run out of memory if there isn't enough virtual space.
### Memory allocation
- at start of a new process, the runtime will reserve a contiguous region of address space. 
    - This is called the heap
- All reference types are allocated on the heap.
- reference types are assigned in order
- as long as address space is available the GC continues to allocated space for new objects
- because new objects are allocated consecutively the app can access the object quickly
### Memory release
- the GC engine determines the best time to perform collection.
- when the GC performs a collection, it releases the memory for object that are no longer being used by the app.
- the GC creates a graph that contains all the objects that are reachable from the roots.
- the GC considers unreachable objects as garbage and releases the memory allocated for them. 
- after the unreachable objects' memory is released the GC compacts that reachable objects.
    - memory is compacted only if a collection discovers a significant number of unreachable objects.
- the GC automatically releases the memory for large objects. 
### Conditions for GC
- low physical memory.
- memory usage surpasses a threshold. (adjusted dynamically)
- when the `GC.Collect` method is called
### Managed Heap
- WHen allocating don't use rounded-up values that exceed your needs. (if only need 14 bytes done use a 32 byte int)
- the heap can be though of as 2 heaps
    - the object large 
        - obj of 85,000 and larger (threshold can be configured)
    - the object small
### Generations
- The GC pays attention to:
    - It's faster to compact the memory for a portion of the managed heap
    - New obj have shorter lifetimes and older obj have longer live times
    - Newer obj tend to be related to each other and accessed by the app around the same time.
- GC occurs with short-lived objects.
- there are 3 generations
    - 0, 1 and 2
    - new objs go into 0
    - if an obj survives the first GC it goes into 1
    - same with 1 to 2
- gen 0
    - short lived - gets tossed sooner than later
- gen 1
    - buffer between short and long lived
- gen 2
- Objects that are not reclaimed in GC are surviver and are promoted to the next gen