# Sorting

In many situations we may want to order a set of data in a particular way and for that, we use sorting algorithms. There are many options to choose and languages usually have a default sorting algorithm already implemented for you but it's good to know the different possibilities.

## Examples

- Selection sort
- Bubble sort
- Insertion sort
- Merge sort
- Quick sort
- Merge sort
- Heap sort
- Counting sort
- Radix sort
- Bucket sort
- Tree sort

## Default sorting algorithms

Usually the default algorithm is a mixed algorithm that changes from one to another of the base algorithms to optimize performance. For example, insertion sort is usually a base case for recursive divide-and-conquer sort algorithms like merge sort and quick sort.

Python uses a sorting algorithm called *Tim sort*, which is a combination of merge sort and insertion sort, and C++ uses one called *Intro sort*, which is a combination of quick sort, heap sort and insertion sort.

## Types

### Stable/Unstable

In stable sorting algorithms, the order of elements seen as equal by the sort comparison function remains the same after sorting, i.e. the order of equal elements is preserved after sorting.

Any unstable algorithm can be turned stable by taking position into consideration in the comparison.

#### Examples of stable algorithms by nature
- Insertion sort
- Bubble sort
- Merge sort

### Adaptive/Non-adaptive

In adaptive sorting algorithms, the time complexity of the algorithm changes depending on how ordered the input data is. So if the given data is already sorted, for example, an adaptive algorithm will take linear time and won't reorder any elements.

When the order of elements is unknown beforehand, non-adaptive sorting algorithms are better as they are consistent.

#### Examples of adaptive algorithms
- Insertion sort
- Quick sort
- Bubble sort

#### Examples of non-adaptive algorithms
- Selection sort
- Merge sort
- Heap sort

