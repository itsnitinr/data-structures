---
description: Methods to find one or more missing elements in an array.
---

# Finding Missing Elements

### Single Element Missing :

```c
void findMissing(int a[], int n, int start) {

    int difference = start - 0;
    
    for (int i = 0; i < n; i++) {
        if (a[i] - i != difference) {
            printf("Missing Element : %d\n", i + difference);
            break;
        }
    }

}
```

### Multiple Elements Missing :

```c
void findMissing(int a[], int n, int start) {

    int diff = start - 0;
    printf("Missing Elements :\n");
    
    for (int i = 0; i < n; i++) {
        if (a[i] - i != diff) {
            while (diff < a[i] - i) {
                printf("%d\t", i + diff);
                diff++;
            }
        }
    }

}
```

### Using Hash Array : 

```c
void findMissing(int a[], int n, int high) {

    // Creating and initializing hash array with 0
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
    
    printf("Missing Elements :\n");
    for (int i = low; i <= high; i++) {
        if (h[i] == 0) {
            printf("%d\t", i);
        }
    }

}
```

Contributed by Nitin Ranganath

