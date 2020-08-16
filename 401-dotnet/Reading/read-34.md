# Readings: Review DSA

## LinkedLists
- My goal is to learn the differences between the LinkedList we learned in class and the built in C# LinkedList. The property names and the method signatures are not the same between the linked list we have built in class compared to the C# linked list.

### Properties
- In class - singly linked list 
    - Head <-- Gets the start of the linked list
    - Current <-- Gets the node we are currently looking at.

- Built in - doubly linked list
    - First <-- Gets the first node of the linked list.
    - Last <-- Gets the last node of the linked list.
    - Count <-- Gets the number of nodes actually contained in the linked list.

### Methods
- In class
    - Insert(int value)
        - Adds a new node with the defined value to the beginning of the linked list
    - Includes(int value)
        - Searches the linked list for the value and returns true or false based on if it was found or not.
    - ToString()
        - Overriding the built in ToString method to return all the of the values from the nodes in the linked list.
    - Append()
        - Adds a new node with the defined value to the end of the linked list.
    - InsertBefore(int value, int newValue)
        - Adds a new node to the list before the defined value. newValue is the value of the new node. value is the value of the node we are searching for.
    - InsertAfter(int value, int newValue)
        - Adds a new node to the list after the defined value. newValue is the value of the new node. value is the value of the node we are searching for.
    - KthFromTheEnd(int k)
        - Finds the value of the node of the k's spot from the end.
    - ReverseLinkedList()
        - Reverses the order of the list.

- Built in  


| Method | Description |
| --- | --- |
AddAfter(LinkedListNode<T>, LinkedListNode<T>)	| Adds the specified new node after the specified existing node in the LinkedList<T>.
AddAfter(LinkedListNode<T>, T)	| Adds a new node containing the specified value after the specified existing node in the LinkedList<T>.
AddBefore(LinkedListNode<T>, LinkedListNode<T>)	| Adds the specified new node before the specified existing node in the LinkedList<T>.
AddBefore(LinkedListNode<T>, T)	| Adds a new node containing the specified value before the specified existing node in the LinkedList<T>.
AddFirst(LinkedListNode<T>)	| Adds the specified new node at the start of the LinkedList<T>.
AddFirst(T)	| Adds a new node containing the specified value at the start of the LinkedList<T>.
AddLast(LinkedListNode<T>) | Adds the specified new node at the end of the LinkedList<T>.
AddLast(T)	| Adds a new node containing the specified value at the end of the LinkedList<T>.
Clear()	| Removes all nodes from the LinkedList<T>.
Contains(T)	| Determines whether a value is in the LinkedList<T>.
CopyTo(T[], Int32)	| Copies the entire LinkedList<T> to a compatible one-dimensional Array, starting at the specified index of the target array.
Equals(Object)	| Determines whether the specified object is equal to the current object. (Inherited from Object) 
Find(T)	| Finds the first node that contains the specified value.
FindLast(T)	| Finds the last node that contains the specified value.
GetEnumerator()	| Returns an enumerator that iterates through the LinkedList<T>.
GetHashCode()	| Serves as the default hash function. (Inherited from Object)
GetObjectData(SerializationInfo, StreamingContext)	| Implements the ISerializable interface and returns the data needed to serialize the LinkedList<T> instance.
GetType()	| Gets the Type of the current instance. (Inherited from Object)
MemberwiseClone()	| Creates a shallow copy of the current Object. (Inherited from Object)
OnDeserialization(Object)	| Implements the ISerializable interface and raises the deserialization event when the deserialization is complete.
Remove(LinkedListNode<T>)	| Removes the specified node from the LinkedList<T>.
Remove(T)	| Removes the first occurrence of the specified value from the LinkedList<T>.
RemoveFirst()	| Removes the node at the start of the LinkedList<T>.
RemoveLast()	| Removes the node at the end of the LinkedList<T>.
ToString()	| Returns a string that represents the current object. (Inherited from Object)