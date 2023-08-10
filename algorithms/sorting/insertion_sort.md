# Insertion sort

In this sorting algorithm, we compare adjacent elements continuously to ensure every new element is *inserted* into its correct position in the sorted sub-array at the start. The start sub-array is always sorted but there's no guarantee that they're in their final position, differently from *bubble sort* and *selection sort*. It is *stable* by default.

**Time complexity**: $O(n^2)$. An $O(n)$ loop to go through each new element, performing another $O(n)$ loop each time to place the new element into the sorted sub-array.

**Space complexity**: $O(1)$. It's an in-place algorithm and only needs iteration variables.

## Illustration and description

![Insertion sort of unsorted array of 5 items](/images/insertion_sort.png)

In the image above, we have an unsorted array of 5 items: 15, 2, 8, 4 and 9. Insertion sort will, for every element after the first, insert the new element into the correct place of the sorted sub-array by comparing adjacent elements. For this example, we're sorting in ascending order and it would go like:

1. Compares 2nd and 1st elements: 2 is smaller than 15, so swap them. From this we now the sub-array `{2, 15}` is sorted.

2. Compares 3rd and 2nd elements: 8 is smaller than 15, so swap them. Compares 2nd and 1st elements: 8 is greater than 2, so do no additional swaps. Sorted sub-array: `${2, 8, 15}`.

3. Compares 4th and 3rd elements: 4 is smaller than 15, so swap them. Compares 3rd and 2nd elements: 4 is smaller than 8, so swap them. Compares 2nd and 1st elements: 4 is greater than 2, so do no additional swaps. Sorted sub-array: `${2, 4, 8, 15}`.

4. Compares 5th and 4th elements: 9 is smaller than 15, so swap them. Compares 4th and 3rd elements: 9 is greater than 8, so do no additional swaps. The array is now sorted.

## Implementation

```cpp
void insertion_sort(vector<int>& arr) {
  int i, j, key;

  for (i = 1; i < arr.size(); i++) {
    key = arr[i];

    for (j = i - 1; j >= 0 && arr[j] > arr[i]; j--)
      arr[j + 1] = arr[j];
    
    arr[j + 1] = key;
  }
}
```