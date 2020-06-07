# Read: 09 - Refactoring
#### 6/6/20

- [Concepts of Functional Programming](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)
- [Fun With Refactoring](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec)

## Concepts of Functional Programming
- Trying to make software less complex
- Trying to build side-effect-free functions.

### What is functional programming?
- A style of building the structure and elements of a program that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.
### Pure functions
- A function always returns the same result if gent the same arguments. (deterministic)
    - No external objects
- Does not cause any observable side effects.  
    - Any function that relies on a random number generator can not be pure but it will not cause any *observable side effects*.
    - Mutability is discouraged
### Benefits
- Code is easier to test
### Immutability
- Unchanging over time or unable to be changed.
    - Use forEach since it can't change the original array.
### Referential transparency
- The same input always gives the same output
- pure functions + immutable data = referential transparency
### Functions as first-class entities
- functions are also treated as values and used as data.
- Functions as first-class entities can:
    - refer to it from constants and variables
    - pass it as a parameter to other functions
    - return it as result from other functions
### Higher-order functions
- takes one or more functions as arguments
- returns a function as its result
### Filter
- Imperative approach
    - not functional programming
- Declarative approach
    - more functional
### Map
### Reduce

## Fun with Refactoring
### Strategies
- Return early from functions
- Cache variable so functions can be read lik sentences.
- Check for Web APIs before implementing your own functionality