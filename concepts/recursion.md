# Recursion

A recursive function is a function that calls itself. Prime examples of recursive functions are the factorial and the fibonacci sequence. On every iteration, the function either calls itself or reaches a base case, from where all previous calls get essential information from. It's very useful, for example, for backtracking and divide-and-conquer algorithms.

```cpp
int factorial(int n) {
  if (n <= 1)
    return 1;
  return n * factorial(n - 1);
}

int fibonacci(int n) {
  if (n <= 1)
    return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```