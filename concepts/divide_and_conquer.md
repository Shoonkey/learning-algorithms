# Divide and Conquer algorithms

*Divide and conquer* algorithms 

1. *divide* the main problem into smaller sub-problems of the same type
2. *conquer* by recursively solving the subproblems
3. *combine* the answers to achieve the result of the main problem.

> This type of algorithm generates two or more subproblems from the main one. If it only generates one subproblem, like in [binary search](/algorithms/binary_search.md), it is a [decrease and conquer](/concepts/decrease_and_conquer.md) algorithm.

## Example

[Merge sort](/algorithms/sorting/merge_sort.md) is an example of a divide-and-conquer algorithm as it takes the problem of sorting an array and works by *dividing* it into sub-arrays until they're composed of a single element (which in a way is always a sorted array) and then *conquers and combines* by joining the sorted sub-arrays into the main sorted one.