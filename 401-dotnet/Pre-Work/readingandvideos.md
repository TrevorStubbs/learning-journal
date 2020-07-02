# Prework - Readings & Videos

- [C# Version History](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-version-history)
- [.Net Core Guide](https://docs.microsoft.com/en-us/dotnet/core/)
- [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet)
- [What is a .NET Hello World App?](https://www.youtube.com/watch?v=uKoqBCyFATw&list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80&index=3)
- [Basic Debugging](https://www.youtube.com/watch?v=feWeInify18&list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80&index=4)
- [What is Managed Code](https://docs.microsoft.com/en-us/dotnet/standard/managed-code)
- [What is the CLR](https://docs.microsoft.com/en-us/dotnet/standard/clr)
- [Introduction to the C# Language and the .NET Framework](https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)
- [C# Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/)

## History of C#
### Version 1.0 
- looked a lot like Java
- Lacked built-t async capabilities.
### 2.0
- added
    - gernerics
    - partial types
    - anonymous methods
    - nullable value types
    - getter/setter
### 3.0
- lamda expressions
- query expressions
    - linq
- anonymous types
### 4.0
- named/optional arguments
- generic covariant and contravariant
### 5.0
- Asynchronous members
    - `async` and `await`
### 6.0
- static imports
- null propagator
- string interpolation
- nameof operator
### 7.0
- tuples and deconstruciton
- pattern matching
- throw expressions
- 1_000_000 is readable by the compiler and will ignore the _
### 7.1
- async Main method
### 7.2
### 7.3
### 8.0
- new CLR with .NET Core.

---

## .NET Core
- open-source: MIT and Apache 2 licenses
    - .NET Foundation project
- cross platform: windows, macOS, and linux
- can work in x64, x86 and ARM
- can use C#, Visual Basic and F#
- APIs
    - ASP.NET Core
    - Xamarin
    - System.Device.GPIO
    - ML.NET
- .NET Core SDK
    - .NET Core CLI
    - .NET Core libraries and runtime
    - The dotnet driver

## What is .NET
- A Platform
    - .NET Core
    - .NET Framework
    - Xamarin/Mono
- Languages 
    - C#
    - Visual Basic
    - F#
- .NET standard
    - a base set of APIs
- Libraries

## .NET Core
## Debugging
- conditional breakpoint
    - gear icon
- step over
- step into
- release vs debug
    - release: trimmed down (optimized)
    - debug: for working code
## Managed Code
- code that is managed at runtime.
    - the CLR takes the managed code, compiles it and executed it. 
    - Provides automatic memory management, security boundaries, type safety, etc.
    - the CLR take care of the management of the code (unlike C/C++)
- Intermediate language (IL)
    - compiled C# turns into a IL binary
    - Just-In-Time compiling
- Interoperability 
    - Code that doesn't run to the IL

## Common Language Runtime (CLR)
- JIT compiling
- metadata is stored with the code.
- handles object layout and manages references to objects and releasing them when they are no longer being used. 

## Intro to C# and .NET Framework
- Expressive syntax
- supports generic methods and types
- LINQ Language-Integrated Query
- OOP
    - encapsulation
    - inheritance
    - polymorphism
- Insertion point is `main`
- Methods that override virtual methods in a parent class require the `override` keyword to prevent redefinition.
- Structs act like a lightweight class
- Can interact with Window software like COM (Component Object Model) and native Win32 DLLs.
- C# supports pointers and 'unsafe' code for direct memory access.
- no header files
- methods and types don't have to be declared in a specific order
- C# can interact with code written in Visual Basic or Visual C++ if they are run on .NET Framework

## C# Arrays
``` C#
type[] arrayName;

// Declare a single-demensional array
int[] array1 = new int[5];

// Declare and set array element values
int[] array2 = new int[] { 1, 2, 3, 4, 5 };

// Alt syntax
int[] array3 = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 0 };

//Declare a 2 dimensional array
int[,] multiDimensionalArray1 = new int[2, 3];

// Declare and set elements in a 2 dimensional array
int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

//Declare a jagged array
int[][] jaggedArray = new int[6][];

// Set the values of the first array in the jagged array.
jaggedArray[0] = new int[4] { 1, 2, 3, 4 };
```

## C# 7.0 in a Nutshell
### Chapter 1: Introducing C# and the .NET Framework
- Unified Type System
    - all types share a common base type
        - `ToString()`
- Classes and interfaces
    - does not support multiple inhertance of classes
    - but can inherit muptipl interfaces
- Has elements of functional programming
    - functions can be treated as values `delegates`
    - Supports patterns for puity
#### Type Safety
- static typing
- strongly typed language
#### Memory Management
- Garbage collection
#### C# and the CLR
- JIT compilation
#### The CLR and .NET Framework
#### Other Frameworks
- It's possilbe to run managed code inside SQL server.
#### Windows Runtime (WinRT)
- languate-neutral object-oriented execution interface
- A set of libraries baked into Windows 8+
- object oriented libraries the essential part of Win10.

- what are out variables


### Chapter 2: C# Language Basics