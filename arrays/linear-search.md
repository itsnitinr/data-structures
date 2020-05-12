---
description: Implementation of linear search and methods to improve it
---

# Linear Search

### Basic Linear Search 

In linear search, each element of the array is scanned through a for loop and is checked if it same as the element that is to be found i.e key. If found, the index at which the element was found is returned or else, -1 is returned.

**Time Complexity : O\(n\)**

```c
int linearSearch(struct Array arr, int key) {
    
    for (int i = 0; i < arr.length; i++) {
        if (arr.A[i] == key) {
            return i;
        }
    }
    return -1;
    
}
```

### Improving Linear Search

Linear search can be improved by two techniques : 

* Transposition method
* Move to head

### Transposition Method

This method works on the concept that if an element is searched for in an array, chances are that it may be searched for again. Therefore, before returning the index of found element, we swap the element with \(i-1\)th element and return i-1 instead of i.

```c
int linearSearch(struct Array *arr, int key) {

    for (int i = 0; i < arr -> length; i++) {
        if (arr -> A[i] == key) {
            swap(&arr -> A[i], &arr -> A[i-1]);
            return i-1;
        }
    }
    return -1;    

}

void swap(int *x, int *y) {
    int temp;
    temp = *x;
    *x = *y;
    *y = temp;
}
```

### Move to Head

This method is similar to transposition method except that the found element is swapped with first element i.e 0th index element instead of \(i-1\)th element. This reduces the time complexity on searching the same element to O\(1\).

```c
int linearSearch(struct Array *arr, int key) {

    for (int i = 0; i < arr -> length; i++) {
        if (arr -> A[i] == key) {
            swap(&arr -> A[i], &arr -> A[0]);
            return 0;
        }
    }
    return -1;    

}

void swap(int *x, int *y) {
    int temp;
    temp = *x;
    *x = *y;
    *y = temp;
}
```

Contributed by Nitin Ranganath

