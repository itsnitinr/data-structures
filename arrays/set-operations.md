---
description: >-
  Implementation of set operations like union, intersection, difference and set
  membership.
---

# Set Operations

### Union Operation :

To get the union of two arrays, apply merge procedure such that if an element is present in both arrays, **copy it to the merged array once and increment both i and j**.

```c
void unionOfArray(int a[], int b[], int c[], int n1, int n2) {
    
    // Index pointers 
    int i = 0, j = 0, k= 0;
    
    while (i < n1 && j < n2) {
        // If elements are same, copy once and increment all
        if (a[i] == b[j]) {
            c[k] = a[i];
            i++;
            j++;
        } else if (a[i] < b[j]) {
            c[k] = a[i];
            i++;
        } else {
            c[k] = b[j];
            j++;
        }
        k++;
    }
    
    // Copy remaining elements from first array
    while (i < n1) {
        c[k] = a[i];
        i++;
        k++;
    }
    
    // Copy remaining elements from second array
    while (j < n2) {
        c[k] = b[j];
        j++;
        k++;
    }

}
```

### Intersection Operation : 

In intersection operation, apply merge procedure in such a manner that the **elements are copied only if they are the same or else, their index pointers should just be incremented**. Leftover elements will not be considered.

```c
void intersection(int a[], int b[], int c[], int n1, int n2) {

    int i = 0, j = 0, k= 0;
    
    while (i < n1 && j < n2) {
        // Increment all index pointers if element is same
        if (a[i] == b[j]) {
            c[k] = a[i];
            i++;
            j++;
            k++;
        } else if (a[i] < b[j]) {
            i++;
        } else {
            j++;
        }
    }

}
```

### Difference Operation : 

The difference operation or A-B operation will also follow the merge procedure but in such a manner that **elements will only be copied from the first array and that too only if it is not present in the second array.**

```c
void difference(int a[], int b[], int c[], int n1, int n2) {

    int i = 0, j = 0, k= 0;
    
    while (i < n1 && j < n2) {
        // If elements are same, just increment i and j
        if (a[i] == b[j]) {
            i++;
            j++;
        } else if (a[i] < b[j]) {
        // If element is not same and present in first array,
        // copy it and increment i and k.
            c[k] = a[i];
            i++;
            k++;
        } else {
        // If element is in second array, just increment j.
            j++;
        }
    }
    
    // Copy remaining elements from first array
    while (i < n1) {
        c[k] = a[i];
        i++;
        k++;
    }

}
```

### Set Membership :

For set membership operation, just implement binary search or linear search.

Contributed by Nitin Ranganath

