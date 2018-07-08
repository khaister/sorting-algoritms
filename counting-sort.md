# Counting Sort

> __Input__: a collection of _n_ items, each of which is a non-negative integer whose max value is at most _k_
\
> __Time Complexity__: O(_n_ + _k_) (average/worst)
\
> __Space Complexity__: O(_n_ + _k_), where _k_ is the size of array for storing the counts, _n_ size of array for storing the sorted array

## Characteristics

* Not an in-place sorting algorithm
* Good for non-negative integers sorting
* If k << n, space/time complexity is linear

## Steps

1. Given an input array of integers `in` of size _n_, whose elements are non-negative integers with max values are at most _k_.
2. Create an array of integers, `count`, of size _k + 1_.
3. For each element whose value is _v_ in input array, increase the element at `count[v]` by 1.
4. Create an output array `out` of size _n_.
5. For each value of the `count` array whose index is _i_ and value is _v_, write _i_ to the output array `in` _v_ times.

## Implementations

```java
int[] countingSort(int[] array, int arraySize, int maxElementValue) {
    int[] count = new int[maxElementValue + 1];
    for (int number : array)
        count[number]++;

    int[] sortedArray = new int[arraySize];
    int currentSortedIndex = 0;
    for (int i = 0; i < count.length; i++)
        for (int j = 0; j < count[i]; j++) {
            sortedArray[currentSortedIndex] = i;
            currentSortedIndex++;
        }

    return sortedArray;
}
```
