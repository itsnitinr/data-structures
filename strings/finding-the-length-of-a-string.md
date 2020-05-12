---
description: Implementation for finding the length of a string without library functions.
---

# Finding the Length of a String

### Procedure :

* Take character array / pointer as input
* Iterate through the array until null terminator \(\0\) is not encountered.
* Increment length in each iteration.
* Return length

```c
int findLength(char *a) {

    // Variable to track length
    int len = 0;
    
    // Iterate till null character is not found
    for (int i = 0; a[i] != '\0'; i++) {
       len++; 
    }
    
    return len;

}
```

Contributed by Nitin Ranganath

