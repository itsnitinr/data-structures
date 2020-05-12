---
description: >-
  Implementation of binary search in array using iterative as well as recursive
  method.
---

# Binary Search

Binary search is a searching technique which is considered to be better than linear search as the array size keeps getting smaller and smaller in each iteration or recursive call and the index of found element can be found in fewer steps as compared to linear search.

 **Time Complexity = O\(log n\)**

### Iterative Method

```c
int binarySearch(int a[], int low, int high, int key) {

    while (low <= high) {
    
       int mid = (low + high)/2; 
       
       if (a[mid] == key) {
           return mid;
        } else if (a[mid] > key) {
            // Key lies in the left sublist
            high = mid - 1;
        } else {
            // Key lies in the right sublist
            low = mid + 1;
        }      
    
    }
    
    return -1;

}
```

### Recursive Method

```c
int binarySearch(int a[], int low, int high, int key) {

    if (low <= high) {
        
        int mid = (low + high)/2;
        
        if (a[mid] == key) {
            return mid;
        } else if (a[mid] > key) {
            // Key lies in left sublist
            return binarySearch(a, low, mid-1, key);
        } else {
            // Key lies in right sublist
            return binarySearch(a, mid+1, high, key);
        }
        
    }
    
    return -1;

}
```

In this case, it is better to use iterative version of binary search as recursion uses internal stack. However, the time complexity remains the same for both the methods.

Contributed by Nitin Ranganath

