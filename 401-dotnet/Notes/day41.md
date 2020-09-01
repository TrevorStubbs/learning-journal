# Day 41

## Whiteboard
## Problem domain
- Don't be verbose
    - listen to the problem

### Visual
- Have a happy path
- have a non happy path
- Be as clear as possible
- ask questions
    - singly/doubly
    - in place
    - datatypes
        - if strings
            - does upper case count?
    -  is it sorted?

## Algorithm
- write a list of tools needed
- write a list of variables that are needed
- write a list of the comparators
- write a list of loops

- Track how dups are found

```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```