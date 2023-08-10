# Bubble sort

In this sorting algorithm, we compare adjacent elements continuously and swap them if necessary to ensure the n-th last element is moved to its final, correct position. At the end of the n-th iteration, the last n elements are in their sorted, final position. It is *stable* by default.

If at any given step no swaps were done it means the array is already sorted.

**Time complexity**: $O(n^2)$. An $O(n)$ loop where the n-th last element is placed at its final sorted position by swapping adjacent elements until it gets there, which requires another $O(n)$ loop.

**Space complexity**: $O(1)$. It's an in-place algorithm, requires iteration variables, a variable for swapping and a variable to store if any swaps were made so that it breaks as soon as the array is sorted.

## Illustration and description

![Bubble sort of unsorted array of 5 items](/images/bubble_sort.png)

In the example we have an unsorted array built of 15, 2, 8, 4 and 9. Bubble sort will:

1. Compare, and swap if necessary, all adjacent elements from first (0) to last (n - 1), which will result in 15 moving to the last position. A swap happened on all comparisons, so the array is now `{2, 8, 4, 9, 15}`. We can now ignore the last 1 element on next iterations as it is part of the sorted sub-array.

2. Compare, and swap if necessary, all adjacent elements from first to second to last (n - 2), as the last one is already at its final sorted position. This will result in 8 and 4 swapping and 9 staying at its final sorted position. Array is now `{2, 4, 8, 9, 15}`. We can now ignore the last 2 elements on next iterations.

3. Compare, and swap if necessary, all adjacent elements from first to third to last (n - 3). No swaps will be necessary here which means the array is now fully sorted. `{2, 4, 8, 9, 15}`.

## Implementation

```cpp
void bubble_sort(vector<int>& arr) {
  bool swapped;
  for (int i = 0; i < arr.size() - 1; i++) {
    swapped = false;
    for (int j = 0; j < arr.size() - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        swap(arr[j], arr[j + 1]);
        swapped = true;
      }
    }

    if (swapped == false)
      break;
  }
}
```