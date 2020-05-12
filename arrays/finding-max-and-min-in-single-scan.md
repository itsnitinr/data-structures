---
description: >-
  Implementation for finding the maximum and minimum element in an array in a
  single scan itself.
---

# Finding Max & Min in Single Scan

### Procedure : 

* Take array and array size \(n\) as input
* Assign max and min variable to first element initially.
* Iterate from index = 1 to n
* If the element at index 1 is less than min, change min value.
* If not, check if it greater than max. If so, change max value.

```c
void findMinMax(int a[], int n) {

    // Assign min and max to first element
    int min = a[0];
    int max = a[0];
    
    for (int i = 1; i < n; i++) {
        // If current element is less than min, update min.
        if (a[i] < min) {
            min = a[i];
        }
        // If current element is greater than max, update max.
        else if (a[i] > max) {
            max = a[i];
        }
        
    }
    
    printf("The maximum element is %d\n", max);
    printf("The minimum element is %d\n", min);

}
```

Contributed by Nitin Ranganath

