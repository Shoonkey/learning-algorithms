# Merge sort

In this sorting algorithm, the unsorted array is continuously split in half until the sub-arrays have only one element and then the sub-arrays are merged into the sorted version of the parts. It is *stable* by default.

Merge sort is good for sorting large datasets as it takes consistently $O(n\ log\ n)$ time to run, on all cases. It's also *parallelizable*, which means it can use multiple processors or threads. It can be used for external sorting, when the data is so large it can't fit into main memory (usually RAM).

**Time complexity**: $O(n\ log\ n)$. This algorithm is recursive, divides the array into halves and for each 2 sorted sub-arrays it performs a linear-time merge operation. Thus it can be expressed as the recurrence relation $T(n) = 2T(n/2) + \Theta(n)$, which can be solved by the Recurrence Tree method or the Master method (case 2), giving the result $\Theta(n\ log\ n)$.

**Space complexity**: $O(n)$. This algorithm is **not** in-place. To perform the merges, it constructs two sorted sub-arrays that it merges into one.

## Illustration and description

![Merge sort of an unsorted array of 5 items](/images/merge_sort.png)

1. Divides into halves until no further division can be done, resulting in the sub-arrays `{15}`, `{2}`, `{8}`, `{4}` and `{9}`.

2. Merges sub-arrays, making `{2, 15}`, `{8}` and `{4, 9}`.

3. Merges sub-arrays, making `{2, 8, 15}` and `{4, 9}`.

4. Merges sub-arrays, making the fully sorted array `{2, 4, 8, 9, 15}`.

## Implementation

```cpp
void merge(vector<int>& arr, int p, int q, int r) {
  // Create sub-arrays L = arr[p..q] and M = arr[q+1..r]
  
  int n1 = q - p + 1;
  int n2 = r - q;

  int L[n1], M[n2];

  for (int i = 0; i < n1; i++)
    L[i] = arr[p + i];
  for (int j = 0; j < n2; j++)
    M[j] = arr[q + 1 + j];

  // Merge arr[p..q] and arr[q+1..r]) into arr[p..r]

  // Part 1. Merge the two sorted sub-arrays until the end of either sub-array is reached.

  int i, j, k;
  i = 0;
  j = 0;
  k = p;

  while (i < n1 && j < n2) {
    if (L[i] <= M[j]) {
      arr[k] = L[i];
      i++;
    } else {
      arr[k] = M[j];
      j++;
    }
    
    k++;
  }

  // Part 2. Pick up remaining elements from the sub-array whose end wasn't reached

  while (i < n1) {
    arr[k] = L[i];
    i++;
    k++;
  }

  while (j < n2) {
    arr[k] = M[j];
    j++;
    k++;
  }
}

void merge_sort(vector<int>& arr, int l, int r) {
  if (l >= r)
    return;
 
  int mid = l + (r - l) / 2;

  merge_sort(arr, l, mid);
  merge_sort(arr, mid + 1, r);

  merge(arr, l, mid, r);
}
```