# Day 10: Career Day 2
#### 7/17/20

## Stacks and Queues
### Stacks
- FILO - First in last out (most common)
- LIFO - last in first out

- operations
    - Push - onto stack
        - O(1)
    - Pop off the stack
        - always peek before pop
        - O(1)
    - Peek - just look
        - return top.Value;
        - O(1)

        1-7


- no traversal in stacks
- all items at bottom are not seen

- Top - stack
    - linked list uses - head
    - queue uses - front

### Queues
- a line of people

- private rear
- front is private
- enqueue attactch to the rear.
- dequeue remove something from the queue
- FIFO - first in first out
- LILO - Last in last out

- enqueue
- dequeue
- peek shows the value of the front node

- Enqueue(Value)
    - create a new node
    - rear.Next = newNode
    - rear = newNode

- return Node Dequeue(value)
    - temp = front
    - front = front.next
    - temp.Next = null
    - return temp

- peek()
    - return front.value