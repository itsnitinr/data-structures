---
description: Implementation of 2 of the methods which can be used to reverse an array.
---

# Reversing an Array

### Reversing Techniques :

* Reversing using Auxiliary Array
* Reversing by Swapping Elements

### Reversing Using Auxiliary Array :

In this method, we create a new array which stores the values of the input array in reverse order and then overwrites the input array with newly created array.

```c
void reverseByCopy(int a[], int n) {

    int i, j, b[n]; // New array to store in reverse order
    
    // Storing elements in 'b' array in reverse order
    for (i = n-1, j = 0; i >= 0; i--, j++) {
        b[j] = a[i];
    }
    
    // Overwriting 'a' array 
    for(int i = 0; i < n; i++) {
        a[i] = b[i];
    }
    
}
```

### Reversing by Swapping Elements :

In this method, we keep swapping the left side and right side elements of the array until all the elements are swapped.

```c
void reverseBySwap(int a[], int n) {

    int i, j;
    
    // i is set to left end, j is set to right end
    for (i = 0, j = n-1; i < j; i++, j--) {
        int temp = a[i];
        a[i] = a[j];
        a[j] = temp;
    }
    
}
```

Contributed by Nitin Ranganath

