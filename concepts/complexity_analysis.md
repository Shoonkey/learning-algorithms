# Complexity analysis

As you code there may arise the need for optimization and it is always good to build with performance in mind and to ensure this
code can be analysed relative to the input.

Every algorithm has a time complexity and a space complexity, regarding the time and space they take in relation to the input.
An algorithm can have a worst case (say in a linear search we iterate through all elements of a list and don't find a match),
a best case (we find a match in the first check) and an average case (we find a match somewhere in the middle). They're notated as:

- Best case (or lower bound): $\Omega(n)$ - "omega of n"
- Worst case (or upper bound): $O(n)$ - "big-oh of n"
- Average case: $\Theta(n)$ - "theta of n"

There are many different complexities. The most common are:

- $O(1)$, constant. Say an algorithm just does some basic arithmetic checks (like `x < 3 && x > 5`), then it has constant time
complexity. An algorithm that stores a bunch of helper variables (no arrays or lists) it uses for an operation has constant space complexity.

- $O(log\ n)$, logarithmic. Common time complexity for divide and conquer algorithms, like binary search.

- $O(n)$, linear. A simple example is linear search: say we want to search an unsorted list, we can iterate through the list one by one
looking for the match, taking at most $n$ checks (assuming matching has constant time complexity).

- $O(n^2)$, quadratic. Some sort algorithms, like bubble sort or insertion sort.

An algorithm may chain many sub-algorithms which have their own complexities and result in the algorithm having their combined complexity.