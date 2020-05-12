---
description: Obtaining a pair of elements in the array whose sum = k.
---

# Getting a Pair whose Sum = K

### For Sorted Arrays:

```c
void findPair(int a[], int n, int key) {

    // Set i to starting index and j to last index
    int i = 0, j = n-1;
    
    while (i < j) {
        // If pair is found, increment i and decrement j
        if (a[i] + a[j] == key) {
            printf("Pair : %d and %d\n", a[i], a[j]); 
            i++;
            j--;
        }
        // If sum is greater than key, decrement j
        else if (a[i] + a[j] > key) {
            j--;
        }
        // If sum is smaller than key, increment i
        else {
            i++;
        }
        
    }

}
```

### For Unsorted Arrays:

```c
void findPair(int a[], int n, int max, int key) {
    
    // Create and initialize hash array with 0
    int h[max];
    for (int i = 0; i < max; i++) {
        h[i] = 0;
    }
    
    for (int i = 0; i < n; i++) {
        // Check if the suitable pair is present
        if (h[key - a[i]] != 0) {
            printf("Pair : %d and %d\n", a[i], key-a[i]);
        } 
        h[a[i]]++;
    }

}
```

Contributed by Nitin Ranganath

