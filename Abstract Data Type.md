
```ad-info
title: Abstract 
It means hiding internal details
```

```ad-info
title: Data Type
Defined by:
1. Representation of data (how data is stored in memory).
2. Operations allowed on data
```
Example: `int` in C++
1. Representation: 2 bytes (16 bits), 1 bit for sign, 15 bits for number.
2. Operations: Arithmetic`(+, -, *, /, %)`, Relational `(<, >, ==)`, increment/decrement `(++/--)`.

```ad-Definition
title: Abstract Data Type
It combines data representation and operations and allows us to use data type without knowing internal details.

Note: ADT is related to OOPs so classes in C++ can define ADTs
```
All data structures (array, linked list, stack, queue, tree, graph, hash table) can be represented as ADTs.


```ad-example
title: List ADT
1. Representation Needed: 
  * Space to store elements
   * Capacity (max size)
   * Current size (number of elements)
     
2. Representation methods: array or linked list.
   
3. Operations Needed

Add / Append: Add element at the end.
Insert / Add at index: Add element at a specific index (shift elements as needed).
Remove: Remove element at an index (shift elements).
Set / Replace: Change element at a given index.
Get: Access element at a given index.
Search / Contains Key: Find index of a given element.
Other operations: Sort, reverse, merge, split, etc.


```