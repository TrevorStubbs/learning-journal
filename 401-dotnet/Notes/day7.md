# Day 7

## Review
- 2 types of classes
  - abstract and concrete

## Polymorphism
- Most complex
- Most used
- Ability to change behaviors and properties of base classes
- standardize on "types"
    - `if (cat is Animal)`

- 4 types of Methods
    1. Concrete - can live in all classes
    1. Abstract - only live in abstract methods 
        - declaring a method signature but no implementation of behavior
        - requires the first non abstract class to implement behavior
        - required override
    1. Virtual - optional to override
        - can live in all classes
    1. Sealed - making a method read only
        - derived classes cannot override the sealed method
    
## Encapsulation
1. contain
    - group together
    - protect
1. Permissions
    1. public - no restrictions
    1. Private - Only the class can access
        - no derived
    1. Protected - Class and it's dervied classes
        - at or below
        - never above
    1. Internal - accessible to whole assembly
    1. Protected Internal
    1. Private Protected.