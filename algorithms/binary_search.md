# Binary search

Binary search is a technique that allows for searching in a *sorted* array, in $O(log\ n)$ time, by repeatedly cutting the search range in half until element is found or no. It uses the fact the array is sorted to assume all elements in the discarded half can't be the element.

For example, take the array `{ 1, 4, 5, 8, 9, 10, 12, 15 }`.

If we're looking for 1, we can start looking in the middle of the array, where we'll find 8. As the array is sorted, we know all elements after 8 are greater or equal to 8, but we're looking for 1, therefore we can look in the range `{1, 4, 5}`. Repeating the same logic, we find 4 in the middle, but $4 > 1$ so we can check in the range `{1}`, where we find 1.

The algorithm optimizes the search process by taking advantage of the sortedness of the data.

## Implementations

### Recursive
```cpp
bool binary_search(vector<int>& arr, int value, int start, int end) {
  if (start > end)
    return false;
  
  // same as (start + end) / 2 but somewhat avoids integer overflow
  int mid = start + (end - start) / 2;

  if (arr[mid] == value)
    return true;
  
  if (arr[mid] < value)
    return binary_search(arr, value, mid + 1, end);
  else
    return binary_search(arr, value, start, mid - 1);
}

```

### Iterative
```cpp
bool binary_search(vector<int>& arr, int value) {
  int start = 0;
  int end = arr.size() - 1;
  int mid;

  while (start <= end) {
    // same as (start + end) / 2 but somewhat avoids integer overflow
    mid = start + (end - start) / 2;

    if (arr[mid] == value)
      return true;
    if (arr[mid] < value)
      start = mid + 1;
    else
      end = mid - 1;
  }

  return false;
}
```