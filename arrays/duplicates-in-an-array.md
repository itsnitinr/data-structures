---
description: Procedure to find and count duplicates in an array.
---

# Duplicates in an Array

### Finding Duplicates in a Sorted Array:

```c
void findDuplicates(int a[], int n) {

    int lastDuplicate = 0;
    printf("Duplicates in the array :\n");

    for (int i = 0; i < n; i++) {
        // If two or more same elements appear consecutively
        if (a[i] == a[i+1] && lastDuplicate != a[i]) {
            printf("%d\t", a[i]);
            // Keeping track of latest duplicate to avoid
            // printing the same duplicate again
            lastDuplicate = a[i];
        }
    }
    printf("\n");
    
}
```

### Counting Duplicates in a Sorted Array:

```c
void countDuplicates(int a[], int n) {

    int j;
    printf("Duplicates in the array :\n");

    for (int i = 0; i < n-1; i++) {
        if (a[i] == a[i+1]) {
            // Start counting duplicates from i + 1
            j = i + 1;
            while (a[i] == a[j]) {
                // Finding the number of duplicates
                j++;
            }
            printf("%d is appearing %d times\n", a[i], j-i);
            // Start looking for duplicates again
            i = j - 1; 
        }    
    }

}
```

### Using Hash Array:

```c
void findAndCountDuplicates(int a[], int n, int high) {

    // Creating a hash array and initializing with 0
    // Size of hash array = maximum element in input array
    int h[high];
    for (int i = 0; i < high; i++) {
        h[i] = 0;
    }
    
    // Incrementing hash table values as per the numbers in
    // original input array
    for (int i = 0; i < n; i++) {
        h[a[i]]++;
    }
    
    // If any element in hash table has value > 1,
    // it means that the element is repeated
    for (int i = 0; i <= high; i++) {
        if (h[i] > 1) {
            printf("%d appears %d times\n", i, h[i]);
        }
    }

}
```

Contributed by Nitin Ranganath

