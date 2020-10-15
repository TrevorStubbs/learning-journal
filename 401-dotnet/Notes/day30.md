# Day 30
## Hash Tables

- O(1) lookup
- O(n) hashing
    - if collisions O(log<sub>n</sub>)

- Collisions
    - microsoft based hashtables don't have collisions. 
    - could make a tree at a bucket

- Dedupe a linked list (remove the duplicates)

- hashset 
    - first come first serve.
    - collisions are not allowed

- Built in C# Hashtable is a dictionary.

- Methods
    - Add(key, value)
    - Find(key)
    - Contains(key)
    - GetHash(key) - returns an integer (private)