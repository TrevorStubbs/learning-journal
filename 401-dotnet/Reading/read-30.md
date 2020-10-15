# Read: Hash Tables

- [Intro to Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)
- [what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)
- [basics of hash tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
- [hash table wiki](https://en.wikipedia.org/wiki/Hash_table)


## Intro to Hash Tables
### Terms
1. Hash - Used to determine the index of an array
1. Buckets - Is what is contained in each index of the array. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
1. Collision - A collision is what happens when more than 1 key gets hashed to the same location of the hashtable.

### Why
1. Hold unique values
1. Dictionary
1. Library

### What
- Each Node/Bucket has both a key and a value
- Gives us the ability to store the key into a data structure and quickly retrieve the value. 
- Hash maps have O(1) read access.

### Structure
- Hash code turns a key into an integer.
### Creating a Hash
- A hashtable traditionally is created from an array.
    - Turn a dey into a numeric value
        1. Add or multiply all the ASCII values together.
        2. Multiply it by a prime number (599)
        3. Use modulo to get the remainder of the result, when divided by the total size of the array.
        4. Insert into the array at that index.
``` 
Key = "Cat"
Value = "Josie"

67 + 97 + 116 = 280

280 * 599 = 69648

69648 % 1024 = 16

Key gets placed in index of 16. 
```

### Collisions
- Occurs when more than 1 key hashes to the same index in an array.
    - A perfect hash will never have any collisions
- Collisions are solved by changing the initial state of the buckets.   
    - each bucket would be a linked list
    - now when a collision happens add a node to the linked list.
    - must store both the key and the value

### Store value
- Accept a key
- calculate the has of the key
- use modulus to convert the hash into an array index
- store the key with the value by appending both to the end of a linked list

### Read value
- Accept a key
- calculate the hash of the key
- use modulus to convert th has into an array index
- use the array index to access the short LinkedList representing a bucket
- search the bucket looking for a node with a key/value pair that matches the key you were given.

### Bucket Sizes
- Hash maps can have any number of buckets. If you have a small map there will be many collisions. Larger map will use more space but less collisions.
    - Compute load factor for hashmaps. 

### Internal Methods
- Add()
    1. send the key to the `GetHash` method
    1. Once you determine the index of where it should be place, go to that index
    1. Check if something exists at that index already, if it doesn't, add it with the key/value pair.
    1. If something does exist, add the new new key/value pair to the data structure within that bucket.
- Find()
    - Take in a key, gets that Hash, and goes to the index location specified. Once at the index location is found in the array, it iterates through the bucket and see if the key exists and returns the value.
- Contains()
    - accept a key, and return a bool on if the key exists inside the hashtable. The best way to do this is to have the contains call the `GetHash` and check the hashtable if the key exists in the table given the index returned.
- GetHas()
    - accept a key as a string, conduct the has, and then return the index of the array where the key/value should be placed. 
