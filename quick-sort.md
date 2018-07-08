# Quick Sort

> __Time Complexity__: O(_n_ lg _n_) (average) and O(n^2) (worst)

## Characteristics

* Efficient in practice
* In-place

## Steps

1. If the input array, _a_, has 5 or fewer elements, sort it using insertion sort.
2. Find an array element _M_ = a[q] (called the _pivot_), which will split the array into approximately two equal _partitions_, such that each element in the first partition is less than or equal to (leq) _M_ and each element in the second partition is greater than _M_.
3. Partition _a_ by swapping any elements that are leq _M_ to the left side of _a_, and all elements greater than _M_ to the right side of _a_.
4. Recursively sort each side of the array using quick sort.

## Partitioning

```java
int partition(int[] a, int left, int right, int pivotIndex) {
    int pivotValue = a[pivotIndex];
    swap(a[pivotIndex], a[right]); // move pivotValue to end

    // Partition the array:
    // Upon finding an element smaller than pivot,
    // swap it to the next position in the 􏰀store􏰁.
    int store = left;
    for (int i = left; i < right; i++) {
        if (list[i] < pivotValue) {
            swap(list[store], list[i]);
            store++;
        }
    }
    swap(list[right], list[store]); // swap pivot to its final position.
    return store;
}
```