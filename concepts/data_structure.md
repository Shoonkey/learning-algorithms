# Data structure

A data structure is a way of organizing data so that it can be used effectively. Different data structures have different costs associated with traversing them, adding/removing elements and computing different kinds of operations.

Choosing a good data structure is very important to the performance of an algorithm. Say we need [memoization](/concepts/memoization.md) for an algorithm, should we use a plain array or a hashmap to store values? It depends on how many elements there will be: if there are many using an array would provide easy and fast access but if there are few there'd be a lot of wasted memory, in which case a hashmap would be better.

## Types of data structure

### Linear/Non-linear
A data structure is *linear* when the data elements are stored in a linear sequence. Linear data structures include array, linked lists, stacks and queues. Non-linear data structures include graphs.

### Static/Dynamic
A data structure is *static* when the size of the structure is fixed, like in a normal array. Non-static data structures are called *dynamic* and include linked lists and hashmaps.

## Examples

- Graphs (trees, linked lists, etc.)
- Arrays
- Stacks
- Queues
- Hashmaps (dictionaries)