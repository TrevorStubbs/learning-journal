# Read: Trees
- [Binary Trees and Binary Search Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

## Common Terminology
- Node - Individual item/data that makes up the data structure
- Root - The top most Node in the tree
- Left Child - The Node positioned to the left of a root or node
- Right Child - The Node positioned to the right of a root or node
- Edge - The edge is the link between a parent and a child node
- Leaf - A node that doesn't contain any children
- Height - The height is determined by the number of edges from the root to the bottom most node

## Traversal
### Depth First
- A traversal where we prioritize going through the depth of the tree first.
- Three methods for depth first traversal:
    - Pre-order: `root >> left >> right` - A, B, D, E, C, F
    - In-order: `left >> root >> right` - D, B, E, A, F, C
    - Post-order: `left >> right >> root` - D, E, B, F, C, A
- most common way to traverse a tree is through recursion.

#### Pre-order
``` Pseudo Code 
ALGORITHM preOrder(root)

  OUTPUT <-- root.value

  if root.left is not NULL
      preOrder(root.left)

  if root.right is not NULL
      preOrder(root.right)
```
- Pre-order means that the root has to be looked at first. In our case, looking at the root just means that we output its value. When we call preOrder for the first time, the root will be added to the call stack.

#### In-order
``` Pseudo Code
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

#### Post-order
``` Pseudo Code
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```

### Breadth First
- A, B, C, D, E, F

- Traditionally, breadth first uses a queue.

``` Pseudo Code
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```

## Binary Tree
- A tree can have any number of children
    - We have been using a binary tree which restricts to only 2 children

- There is no specific sorting order for a binary tree.
    - A node can go to any open spot

### Adding a Node
- One strategy is to fill all spots from top to bottom. 
    - Use of breadth first traversal.
    - Find the first node that doesnt have 2 children
    - and place the new node in that spot.
    - If both spots are empty put the new node in the left most spot.
- In the event you would like to have anode placed in a specific location, you need to reference both the new node and the parent node upon which the child is attached.
### Big O
- Inserting a new node O(n) time
    - O(w) space if we use breadth first w = largest width of the tree
- Searching for a specific node O(n) time
- A 'perfect' binary tree is one where every non-leaf node has exactly 2 children.
    - max width of a 'perfect' tree is `2<sup>(h-1)</sup>` where `h` is the height.

### Binary Search Trees (BST)
- A tree that has a structure
    - Nodes that are smaller than the root are placed to the left
    - Node larger than the root are place to the right.
- Speeds up the Search by comparing the needed value to the root/parent node

#### Big O
- `O(h)` time - h = tree height
- for a perfect tree it's `O(log<sub>n</sub>)` 
    - unbalanced is `O(n)`
- space is `O(1)`