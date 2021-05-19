# Hash Tables

- A Hashtable is an array of a list. Each list is known as a bucket. The position of the bucket is identified by calling the hash() method. A Hashtable contains values based on the key.
- Hashtable contains unique element 
- Hashtable doesn't allow null key or value.
- The initial default capacity of Hashtable class is 11 and this is the bucket size.
- Hashtable stores key/value pair in hash table.
- Key: It is the type of keys given by hash() method.
- Value: It is the type of mapped values that will connect with key.

## The Hierarchy of Hashtable

![images](https://media.geeksforgeeks.org/wp-content/uploads/20201124183400/HierarchyofHashtable.png)
##  hash() method
- it is method we use it to map the value to specific key 
- To achieve a good hashing mechanism
    1. Easy to compute: It should be easy to compute and must not become an algorithm in itself.

    2. Uniform distribution: It should provide a uniform distribution across the hash table and should not result in clustering.

    3. Less collisions: Collisions occur when pairs of elements are mapped to the same hash value. These should be avoided.

## Basic Hash Table Methods
1. The Add Method
    - is used to add items to hash table
2. The Delete Method
    - is used to remove key/value pair objects from the hash table
3. The Get Method
    -  is used to return the value of a provided key.