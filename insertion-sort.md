# Insertion Sort

> __Time Complexity__: O(n^2)
\
> __Space Complexity__: O(1)

## Characteristics

* The "best" of a family of sorting algorithm (but not "best" overall)
* Simple implementation
* Efficient for small data sets
* Adaptive: work better when the input is more partially sorted
* Stable: keep relative order of elements with equal keys
* In-place

## Steps

1. Sort the first item in the sequence.
2. Assume the first i - 1 elements of the sequence are sorted. Move item i left to its appropriate position. Repeat until i = n.

```java
void insertionSort(int[] array, int arraySize) {
    for (int i = 1; i < arraySize; i++) {
        int temp = array[i];

        int j;
        for (j = i - 1; j >= 0; j--) {
            if (array[j] > temp)
                array[j + 1] = array[j];
            else
                break; //index j is where temp belongs
        }
        array[j] = temp;
    }
}
```
