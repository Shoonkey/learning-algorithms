# Selection sort

In this sorting algorithm, we repeatedly check for the lowest (or highest) value in the array and place it in the correct place until all elements are sorted. After the n-th iteration the first n elements are sorted. It is *not stable* by default.

**Time complexity**: $O(n^2)$. An $O(n)$ loop looking for the n-th lowest (or highest) element which takes another $O(n)$ loop.

**Space complexity**: $O(1)$. The algorithm is in-place and takes $O(1)$ auxiliary space for swapping elements.


## Illustration and description

![Selection sort of unsorted array of 5 items](/images/selection_sort.png)

In the image above, we have an unsorted array of 5 items: 15, 2, 8, 4 and 9. Selection sort will look for the n-th lowest (or highest) value in the array and place it in its sorted position. For this example array, it would go like:

1. Smallest value is 2, swap 2 and 15. The sorted subset is `{2}` and the unsorted is now `{15, 8, 4, 9}`.

2. Next smallest value is 4, swap 4 and 15. The sorted subset is `{2, 4}` and the unsorted is now `{8, 15, 9}`.

3. Next smallest value is 8, which is already at the correct place. The sorted subset is `{2, 4, 8}`, unsorted is `{15, 9}`.

4. Next smallest value is 9, swap 9 and 15. The sorted subset is `{2, 4, 8, 9}` and unsorted is `{15}`.

5. As there's only one element in the unsorted it has necessarily been swapped to the correct (last) position. Array is now fully sorted.

## Implementation

```cpp
void selection_sort(vector<int>& arr) {
  int min_idx;
  
  for (int i = 0; i < arr.size() - 1; i++) {
    min_idx = i;

    for (int j = i + 1; j < arr.size(); j++)
      if (arr[j] < arr[min_idx])
        min_idx = j;
    
    if (min_idx != i)
      swap(arr[i], arr[min_idx]);
  }
}
```