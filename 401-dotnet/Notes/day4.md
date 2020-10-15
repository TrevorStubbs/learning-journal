# Day 4

- code call 1:15
- be quick and short. Be an engineer

## OOP
### Classes
- templates
### Objects
- instantiations of a class
- "Object is an instance of a class."

- instance can call static
- a static cant call an instance

## Types in C#
### Value type
- data - hold its own memory allocation
    - ints
    - bools
    - floats
    - doubles
    - NOT STRINGS
- lives on the stack
- GC does not access it

### Reference Type
- Reference (address) to the object
    - its not the object itself
    - reference to where the object lives
- lives on the heap
- Strings, Objects, Classes, Arrays, Interfaces
- `goober` lives on the stack 
    - but references to something in the heap
- default to `null`

### Garbage Collection
- GC triggers
    - memory runs out
    - threshold is hit
    - `GC.Collect`
    

- display board
- make selection
- mulpitpule selection
- what happens when the same position is hit
- 