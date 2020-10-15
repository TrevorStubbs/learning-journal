# Day 34

## Design Patterns

### Architectural Design patterns 
- MVC
- MVVM
- Razor Pages
- Repository Design Patterns

### Code Based Design Patterns
#### Factory
- Abstract Factory
    - 
- Factory Method

- Inheritance
- Abstraction - Client doesn't have to know how to copy a class
- Encapsulation
PolyMorphism

## Data Structure Traversals
- LinkedList - Head
    - Traversals
        - Iterative
        ``` CSharp
        Node current = Head;

        while(curren! = null)
        {
            // Do evaluation here
            current = current.Next;
        }
        ```
            - Current.Next
        - Recursive
        ``` CSharp
        if(current.Next != null)
            method(current.next)
        ```
- Stacks - Top
    - Cannot traverse a stack in place.
    ``` CSharp
    int sum = 0; 
    while(!stack.IsEmpty())
    {
        var temp = stack.Pop()
        sum += temp.Value;
        stack2.Push(temp);
    }
    ```

- Queues - Front
    ``` CSharp
    if(Front.Peek!= null)
    {
        Node First = Front;
        while(front != first);
            var temp = que.Dequeue();
            //Eval
            que.Enqueue(temp);
    }

- Binary Trees - Root (Directive Acyclic Graph)
    - Traversals
        - Depth 
            - PreOrder
                - Root, Left, Right
            - InOrder
                - Left, Root, Right
            - PostOrder
                - Left, Right, Root

        - Breadth - LogN - naturally use a while loop        
            - enqueue root
            - dequeue
            - enqueue the left child 
            - enqueue the right child


        - Iterative
            - use a stack
        - Recursive


    - to make a balanced tree use a breadth first traversal.
        `if(Node.LeftChild == null) { add Node }`
- Binary Search Trees - Root
    - If equal put it right
    - Use a while loop when using a Binary Search Tree.

``` CSharp
while(current.LeftChild != null && current.RightChild != null)
{
    if (current.value == target)
    {
        return true;
    }

    if(current.value > target)
    {
        current = current.LeftChild;
    }

    if(current.value < target)
    {
        current = current.RightChild;
    }

}
return false;
```

