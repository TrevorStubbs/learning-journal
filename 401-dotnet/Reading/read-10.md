# Read: Stacks and Queues

## What is a Stack
- A stack is a data structure that consists of Nodes. Each node references the next node but not the previous
    1. Push - puts a node on the stack
    1. Pop - take a node off the top
        - if the stack is empty an exception is raised.
    1. Top - the top of the stack
    1. Peek - you view the value of the top node of the stack
        - if empty - exception
    1. IsEmpty - returns `true` if the stack is empty

### FILO vs LIFO
- FILO
    - First in Last out - queue
- LIFO
    - Last in First out - stack
### Push O(1)
- push a node onto the stack and assigning it as the new top.
1. create a new node
1. assign `next` to the top item of the stack
1. assign `top` to the new node
``` pseudo 
ALGORITHM push(value)
// INPUT <-- value to add, wrapped in a Node
// OUTPUT <-- none
    node = new Node(value)
    node.next <-- Top
    top <-- Node
```
### Pop O(1)
- Popping a node off the stack
1. Create a reference called temp and point it to the top
1. re-assign `top` to the next node
1. remove the node that temp is pointing to
    - clear `next` of the temp

``` pseudo code
ALGORITHM pop()
//INPUT <-- No Input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty
    Node temp <-- top
    top <-- top.next
    temp.next <-- null
    return temp.value
```

### Peek O(1)
- allows us to inspect the `top` node of the stack
    - check `isEmpty` before conducting a `peek`
```pseudo code
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty
    return top.value
```
### IsEmpty O(1)
``` pseudo code
ALGORITHM IsEmpty()
// INPUT <-- none
// OUTPUT <-- boolean
return top = NULL
```

---

## A Queue
1. Enqueue - nodes being added to the queue
1. Dequeue - nodes being removed from the queue
1. Front - first node of the queue
1. Rear - last node in the queue
1. Peek - retrieve the value of the `front` node in the queue
1. IsEmpty - returns true when the queue is empty else false

- works both in FIFO and LIFO

### Enqueue O(1)
- add an item to the queue
1. change the `next` of the old rear to the node we are adding
1. re-assign `rear` to the new node
``` pseudo code
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
    node = new Node(value)
    rear.next <-- node
    rear <-- node
```
### Dequeue O(1)
- remove an item off the front of the queue
- check `IsEmpty` before conducting a `dequeue`
1. create `temp` reference and point it to the same node `front` is pointing to
1. re-assign `front` to `next`.
    - re-assign `next` property on the `temp` node to `null`
1. return the value of `temp` node
``` pseudo code
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty
    Node temp <-- front
    front <-- front.next
    temp.next <-- null
    
    return temp.value
```
### Peek O(1)
- only inspecting the `front` node of the queue
    - check for `isEmpty`
``` pseudo code
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value
```

### IsEmpty O(1)
``` pseudo code
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return front = NULL
```