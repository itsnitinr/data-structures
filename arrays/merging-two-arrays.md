---
description: Implementation of Merge Algorithm
---

# Merging Two Arrays

### Procedure :

Parameters : 3 arrays \(2 sorted arrays of size n1 and n2 respectively and an empty array of size n1+n2 to merge into\), size of array 1 and size of array 2.

* Initialise i, j and k with 0.
* i is used to keep track of first array, j is used to keep track of second array and k is used to keep track of merged array.
* Compare the values in first array and second array for each index. 
* Assign the lower among those two values to the merged array and increment the index pointers accordingly.
* Transfer remaining elements \(if any\) to the merged array.

### Merge function :

```c
void merge(int a[], int b[], int c[], int n1, int n2) {
    
    // Index pointers to keep track of arrays
    int i = 0, j = 0, k = 0;
    
    // While elements are present in both arrays
    while (i < n1 && j < n2) {
        if (a[i] < b[j]) {
            c[k] = a[i];
            i++;
        } else {
            c[k] = b[j];
            j++;
        }
        k++;
    }
    
    // Transfer remaining elements from first array (if any)
    while (i < n1) {
        c[k] = a[i];
        i++;
        k++;
    }
    
    // Transfer remaining elements from second array (if any)
    while (j < n2) {
        c[k] = a[i];
        j++;
        k++;
    }

}
```

Contributed by Nitin Ranganath

