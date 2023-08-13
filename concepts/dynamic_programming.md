# Dynamic programming

Dynamic programming is an algorithmic approach for optimization problems, just like *greedy algorithms* but is often more complex and slower but guarantees the optimal solution.

It can be applied to efficiently solve problems that involve:

1. **Overlapping subproblems**: Sub-problems share computation which can be memoized to prevent expensive re-calculating.
2. **Optimal substructure**: An optimal solution to the problem contains optimal solutions to the sub-problems.

## Example

A simple example of applying dynamic programming is turning Fibonacci from exponential to linear, using memoization/tabulation. As when calculating the Fibonacci numbers we have overlapping sub-problems (check the [memoization file](./memoization.md) for why that is) and optimal substructure (the optimal solution builds directly upon previous optimal solutions as it is a recurrence relation), dynamic programming is a good fit.

So here's three ways to implement calculating fibonacci numbers:

### Fibonacci purely with recursion

Recursive Fibonacci takes exponential time, $O(2^n)$. It does the full recursion up to the base cases 0 and 1 for every Fibonacci number it recurses through. Notice that we do not make use of the fact some numbers will be calculated more than once, so it is not optimal.

```cpp
int fibo(int n) {
  if (n <= 1)
    return n;

  return fibo(n - 1) + fibo(n - 2);
}
```

### Fibonacci with memoization

We can use memoization to not re-calculate the overlapping sub-problems. Memoization is usually used with recursion and is called a **top-down** approach, meaning we start from what we're trying to find and calculate the value by recursing our way down to the answer.

```cpp
int fibo(int n, unordered_map<int, int>& cache) {
  if (cache.find(n) != cache.end())
    return cache[n];

  int value;

  if (n <= 1)
    value = n;
  else
    value = fibo(n - 1, cache) + fibo(n - 2, cache);

  cache[n] = value;

  return value;
}
```

### Fibonacci with tabulation

We can use tabulation to store past sub-problems so we can use them for solving the next. The difference is that tabulation usually uses iteration and is called a **bottom-up** approach, as we start from the base case and go up towards what we want to find.

```cpp
int fibo(int n) {
  if (n <= 1)
    return n;

  vector<int> values(n + 1);
  values[0] = 0;
  values[1] = 1;

  for (int i = 2; i <= n; i++)
    values[i] = values[i - 1] + values[i - 2];

  return values[n];
}
```