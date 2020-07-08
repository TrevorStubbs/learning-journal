# Read: Linked Lists

- Read: [Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)
- Read: [What’s a Linked List, Anyway pt1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
- Read: [What’s a Linked List, Anyway pt2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

## Linked Lists
- A linked list is a sequence of Nodes that are connected to each other.
- each `node` in the list has a reference to the next `node` in the list
- there are 2 types
    - singly - only forward
    - double - forward and backward

### Terms
1. linked list - A data structure that contains nodes that points to the next node in the list
1. singly - each `node` only has one pointer. 1 that points to the next `node`
1. doubly - each `node` as 2 pointers. 1 to point to the next `node` 1 to point back to the previous `node`
1. Next - a property that contains the reference of the next `node`
1. Head - the first `node` in the list
1. Current - the ``node`` we are currently looking at

### Traversal
- can't use `foreach` or `for`
- we have to use the `next` method in each node
- since we dont really know how long the linked list is we need to use a `while` loop
- we need to check for the `null` at the end of the list
    - `NullReferenceException` will be thrown.
``` pseudo code
ALGORITHM Includes (value)
		// INPUT <-- integer value
		// OUTPUT <-- boolean
			
			Current <-- Head

			WHILE Current is not NULL
				IF Current.Value is equal to value
					return TRUE

				Current <-- Current.Next

			return FALSE
```
1. start with the head
    - make current the head
1. start a while loop
    - make sure current isn't pointing to null
1. if current == to the value we are checking for 
    - return true
1. if current doesn't have what we are looking for   
    - make next current
1. check for null again
1. if we reach the end without finding what we need
    - return false

### Big O
- Time - O(n) - we might have to hit every item in the list.
- Space - O(1) - no extra space is required for the search

### Adding a Node to the beginning
- O(1) - we want to add things to the head
- Steps
    1. Set current to head
    1. instantiate the new node
    1. newNode.Next by default is set to `null`
        - we want to set newNode.Next to `head`
    1. need to re-assign where the new `head` is pointing to
    1. make the new `head` the `current`

``` pseudo code
ALGORITHM Add(newNode)
// INPUT <-- Node to add 
// OUTPUT<-- No output

    Current <-- Head
    newNode.Next <-- Head
    Head <-- newNode
    Current <-- Head
```

### Adding a Node to the middle
- AddBefore or AddAfter
1. make current the node that points to the place we want to be
1. point current to the new node
1. point new node to the next one
```pseudo code
ALGORITHM AddBefore(newNode, existingNode)
    // INPUT <-- New Node, Existing Node
    // OUTPUT <-- No Output

        Current <-- Head

        while Current.Next is not equal to NULL
            if Current.Next.Value is equal to existingNode.Value
                newNode.Next <-- existingNode
                Current.Next <-- newNode

            Current <-- Current.Next;
```
- Big O is O(n)

## What's a Linked List anyway?
### Linear Data Structure
- there is a sequence and an order to how they are constructed and traversed.
    - arrays
    - lists
### Non-linear data structures
- non-sequentially traversal
    - hash/dictionaries
    - trees
    - graphs

### Memory Management
- arrays must be next to eacho ther
    - static data structures
    - always takes up the same amount of memory even if there is nothing in it
    - if needed to grow bigger than its defined size it needs to be copied into a larger structure
- linked lists nodes don't need to be placed next to each other
    - dynamic data structures

### Linked list parts
- made up of nodes
- there usually is a head
- the end of the list isn't a node
    - its a pointer to a null
- each node has 2 parts
    - data - the thing we are storing
    - a reference to the next node
- a node only knows about what data it contains and who its neighbor is.
- each node don't need to live next to each other

### Types of linked lists
- singly
    - one way traversal
- doubly
    - 2 way traversal
- circular linked list
    - no head
    - 1 node acts like a tail

### Big O
- worst case scenario
    - time
    - space
- O(1) - constant
- O(n) - Linear growth
- O(n<sup>2</sup>) - exponential growth

### Big of of LL
- No running out of space 
    - just rearrange pointers
- O(1) to add something at the beginning
- O(n) to add something at the end

### Why or why not?
- "a linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element."<sub>Joshi</sub>
- not good for traversal, iteration or quick index access.
- great for adding a bunch of elements

