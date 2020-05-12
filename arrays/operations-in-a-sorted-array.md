---
description: >-
  Inserting in a sorted array, checking if an array is sorted and shifting
  negative elements to the left of array.
---

# Operations in a Sorted Array

### Inserting in a Sorted Array :

To insert a new element in a sorted array, keep shifting the rightmost elements to the right by 1 until the element to be inserted is not greater than the element to be shifted.

```c
void insertInSorted(int a[], int n, int x) {

    int i = n-1; // Shift from right
    
    // Shifting elements to the right
    while (i >= 0 && a[i] > x) {
        a[i+1] = a[i];
        i--;
    }
    
    // Inserting element in proper position
    a[i+1] = x;
    
}
```

### Checking if an Array is Sorted :

To check if an array is sorted, compare the ith element with \(i+1\)th element and check if ith element is greater than \(i+1\)th element. If it is so, this means that the array is not sorted.

```c
int isSorted(int a[], int n) {

    // Iterate till length - 1
    for(int i = 0; i < n-1; i++) {
        // Case for unsorted array
        if (a[i] > a[i+1]) {
            return 0;
        }
    }
    return 1;
    
}
```

### Rearranging an Array

In this operation, all the negative numbers in the array are moved to the left side of the array while all the positive numbers are moved to the right side of the array.

```c
void rearrange(int a[], int n) {
    
    int j = 0;
    for (int i = 0; i < n; i++) {
        // If negative number => Swap a[i] and a[j]
        if (a[i] < 0) {
            if (i != j) {
                swap(&a[i], &a[j]);
            }
            j++;
        }
    }
    
}
```

Contributed by Nitin Ranganath

