# Binary exponentiation

If we were to implement our own power function `pow`, we could be tempted to do something like:

```cpp
double myPow(int a, int b) {
  if (b == 0)
    return 1;
  if (b < 0)
    return 1 / myPow(a, -b);
  return a * myPow(a, b - 1);
}
```

This is cool and all, and it could also be done iteratively:

```cpp
double myPow(int a, int b) {
  double v = 1;
  if (b > 0)
    while (b--)
      v *= a;
  else
    while (b++)
      v /= a;
  return v;
}
```

But this takes linear time (`O(n)`), and there's a catch that allows us to do it in logarithmic time (`O(log n)`)!
It's called **binary exponentiation**, and it makes use of a cool property of powers to achieve the result faster.

Notice that for an even power, `x^n = (x^2)^(n/2)`, and for odd powers `x^n = x * (x^2)^((n - 1)/2)`. By using that mathematical
property we can cut the time until reached value by 2 on every iteration, thus arriving at log_2 n time.

Using binary exponentiation, the implementation is faster and looks like:

```cpp
double myPow(int a, int b) {
  if (b == 0)
    return 1;
  if (b < 0)
    return 1 / myPow(a, -b);

  if (b % 2 == 0)
    return myPow(a * a, b / 2);

  return a * myPow(a * a, (b - 1) / 2);
}
```
