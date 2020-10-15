# Graphs
- [Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

## Definitions
1. Vertex - Also called a "node", is a data object that can have zero or more adjacent vertices.
1. Edge - A connection between 2 nodes
1. Neighbor - Neighbors of a node are its adjacent nodes (connected by an edge)
1. Degree - The number of edges connected to that vertex.

## Directed vs Undirected Graphs

- Undirected - a graph where each edge is bi-directional.
- Directed Graph (Digraph) - each ege is directed

## Complete, Connected or Disconnected
- A **complete** graph is where all nodes are connected to all other nodes.
- A **connected** graph is a where all vertices have at least 1 edge
- A **disconnected** graph is where some vertices may not have edges.

## Acyclic or Cyclic
- A cycle is when a node can be traversed through and potentially end up back at itself.
- Acyclic Graph 
    - a directed graph without cycles
- Cyclic
    - a graph that has cycles

## Graph Representation
1. Adjacency Matrix
1. Adjacency List

### Adjacency Matrix
- is represented through a 2D array. if there are `n` vertices, then we are looking at a `nxn` Boolean matrix.
- each row and column represents each vertex of the data structure. 
- 1 for an edge
- 0 for no edge
- a *sparse* graph is when there are very few connections.
- a *dense* graph is when there are many connections
- an undirected graph will always be symmetric.
    - not so for directed graph

### Adjacency List - most common
- Is a collection of linked lists or arrays that list all of the other vertices that are connected.
- Adjacency lists make it easy to view if one vertices connects to another

## Weighted Graphs
- A graph with numbers assigned to its edges.
    - These numbers are called weights

## Traversals
### Breadth First
- Breadth first traversal is when you visit all the nodes that are closest to the root as possible.
    - From there you traverse outwards, level by level, until you have visited all the nodes.
- Start at a specific node.
- Need to setup a 'flag' for the nodes that have been visited so that we don't enter an infinite loop.

1. `Enqueue` the declared start node into the queue.
1. create a loop that will run while the queue still has nodes present.
1. `Dequeue` the first node from the queue
1. if the `Dequeue`'d node has unvisited child nodes, mark the unvisited children as visited and re-insert them back into the queue.

``` Pseudo code
ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    breadth.Enqueue(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                child.Visited <-- true
                breadth.Enqueue(child)

    return nodes;
```

- If there are any disconnected nodes (islands) they will not be traversed
- Breadth-first only outputs the nodes that are connected in some relation to the root that you pass in.

### Depth First 
- Use a stack (or recursion)    

1. Push the 'root' node onto the stack
1. Start a while loop while the stack is not empty
1. Peek at the top node in the stack
1. If the top node has unvisited children, mark the top node as visited and then push any unvisited children back onto the stack
1. If the top node does not have any unvisited children, Pop that node off the stack
1. repeat until the stack is empty

