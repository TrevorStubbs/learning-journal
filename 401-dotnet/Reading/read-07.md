# Read: Object Oriented Principles

- [Inheritance](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/inheritance)
- [Abstract](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members)
- [Polymorphism](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/polymorphism)
- [OOP Principles](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/object-oriented-programming)
- C# in a Nutshell - Chapter 3

## Inheritance
- Base class  
    - Parent class
- Derived class 
    - child class
``` C#
class Animal
{
    public string name;
    public int age;
    public float happiness;
}

class Dog : Animal
{
    public Breed breed;

    public Dog (string _name, int _age, float _happiness, Breed _breed)
    {
        name = _name;
        age = _age;
        happiness = _happiness;
        breed = _breed;
    }

    public void Print()
    {
        Console.WriteLine("Name: " + name);
        Console.WriteLine("Age: " + age);
        Console.WriteLine("Happiness: " + happiness);

        Console.WriteLine("Breed: " + breed);
    }
}
```
- An abstract class
    - a class that is never instantiated directly
    - a derived class will inherit from the abstract class    
        - and then will be instantiated

## Abstract and Sealed Classes
- `abstract` keyword declares a class as abstract
    - cannot be instantiated
- `abstract` can be used to declare an abstract method
    - can have no implementation
        - `public abstract void DoSomething(int i);` <- Semicolon
    - derived class can override the virtual method.
```C#
public class Animal
{
    public virtual void DoWork(int i)
    {
        // Original implementation.
    }
}

public abstract class Cat : Animal
{
    public abstract override void DoWork(int i);
}

public class Bengal : Cat
{
    public override void DoWork(int i)
    {
        // New implementation.
    }
}
```
### Sealed Classes
- `sealed`
- a sealed class cannot be used as a base class
    - prevents derivation
    - can make this class run faster
- can be used on a method or property
    - prevents these items from being overridden. 

## Polymorphism
- At run time, instances of a derived class my be treated as instances of a base class.
    - When occurs, the instance's declared type is not longer identical to its run-time type
- Base classes may define and implement `virtual` methods and derived classes can `override` them.

```C#
public class Shape
{
    // A few example members
    public int X { get; private set; }
    public int Y { get; private set; }
    public int Height { get; set; }
    public int Width { get; set; }

    // Virtual method
    public virtual void Draw()
    {
        Console.WriteLine("Performing base class drawing tasks");
    }
}

public class Circle : Shape
{
    public override void Draw()
    {
        // Code to draw a circle...
        // This overrides the base's Draw method
        Console.WriteLine("Drawing a circle");
        base.Draw();
    }
}
public class Rectangle : Shape
{
    public override void Draw()
    {
        // Code to draw a rectangle...
        // This overrides the base's Draw method
        Console.WriteLine("Drawing a rectangle");
        base.Draw();
    }
}
public class Triangle : Shape
{
    public override void Draw()
    {
        // Code to draw a triangle...
        // This overrides the base's Draw method
        Console.WriteLine("Drawing a triangle");
        base.Draw();
    }
}
```
### Poly Overview
- The child class may override virtual members of the base class
- child class inherits the closest base class method without overriding it, preserving the existing behavior but enabling further derived classes to override the method.
- The derived class may define `new` non-virtual implementation of those members that hide the base class implementations.
- fields cannot be virtual
- virtual methods and properties enable derived classes to extend a base class without needing to use the base class implementation of a method. 


## Object-Oriented Programming
- Abstraction means hiding the unnecessary details from type consumers.
- Encapsulation means that a group of related properties, methods, and other members are treated as a single unit or object.
- Inheritance describes the ability to create new classes based on an existing class.
- Polymorphism means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.

- Properties 
```C#
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

- Finalizes
    - used to destruct instances of classes

- Events: Enable a class or object to notify other classes or ob when something occurs
    - use `even` keyword
- Nested Classes
``` C#
class OuterClass
{
    class InnerClass
    {

    }
}
```
- Access modifiers
    - `public` `private` `protected` `internal` `protected internal` `private protected`
- Instantiating use `new`

- Static Classes and Members
    - class level properties and methods
- Anonymous types
``` C#
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

### Interfaces 
- define a set of properties, methods and events
    - provides no implementation
    - represents a contract that a class will implement every aspect of that interface exactly as it is defined. 
``` C#
interface ISampleInterface
{
    void DoSomething();
}
```
### Generics
- can include type parameters that define the types of objects that can be stored or used by that thing.
### Delegates
- A delegate is a type that defines a method signature and can provide a reference to any method with a compatible signature.
- You can invoke the the method through the delegate