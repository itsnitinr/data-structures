---
description: Implementation of reversing a string without using library function.
---

# Reversing a String

### Procedure :

* Calculate the length of string if it isn't given as input.
* Initialise i with 0 and j with length - 1.
* Run a for loop till i &lt; j.
* Swap the i-th and j-th character in each iteration.

### C Function :

```c
void reverse(char a[], int n) {

    // Initialise i with 0 and j with length - 1
    int i = 0, j = n-1;
    char temp;

    // Swap characters in each iteration
    for (i = 0, j = n-1; i < j; i++, j--) {
        temp = a[i];
        a[i] = a[j];
        a[j] = temp;
    }
    
}

```

Contributed by Nitin Ranganath

