# Day 8: 

## Inheritance
- C# allows for multiple lines of inheritance
- Interfaces replace mulitple lines 
- interface: action/verb
    - tells a class what it can do 
    - the class has to implement everything that the interface has
``` C#
interface IFlyable
{
    void landing();
}
class Duck : Bird /*Base class must be first */, ISwim, IFlyable // either fly or flyable
{
    void landing()
    {
        Console.WriteLine("I am landing.");
    }
}
```

- inherit classes
- implementing an interface
    - interfaces are named with an `IFirst`
- override abstract methods - implement an interface method

## Repository Design Pattern
- multiple controllers with dependency injections 

## Enums

## Generics and Collections

## 
- Array.Resize();


