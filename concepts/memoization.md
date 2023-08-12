# Memoization

Memoization is an optimization technique where values of computations that are expensive are cached so they're not re-calculated unnecessarily.

## Example

A simple example is when calculating a Fibonacci number. A Fibonacci number is defined by the function

$$
F(n) = 
  \begin{cases}
    0 & \text{if } n = 0\\
    1 & \text{if } n = 1\\
    F(n - 1) + F(n - 2) & \text{else}
  \end{cases}
$$

If we implement fibonacci recursively there are gonna be overlapping cases, where naturally a value will have to be re-calculated multiple times.

Say we're looking for $F(5)$.

$F(5) = F(4) + F(3)$, so we're calculating $F(4)$ and $F(3)$, but $F(4) = F(3) + F(2)$ and $F(3) = F(2) + F(1)$. Notice how we calculate $F(2)$ twice if we only use the pure recursive implementation. With *memoization*, once we calculate a value, it's not re-calculated again and it is thus more optimized.