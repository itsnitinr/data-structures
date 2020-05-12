---
description: ASCII values and it's importance in changing cases in a string.
---

# Changing Cases in a String

### Common ASCII Codes:

* A = 65
* Z = 90
* a = 97
* z = 122

### The Logic:

To covert from **uppercase to lowercase**, add 32 to the uppercase character.

To convert from **lowercase to uppercase**, subtract 32 from the lowercase character.

### C Function:

```c
void toUpper(char A[]) {
    
    for (int i = 0; A[i] != '\0'; i++) {
        A[i] = A[i] - 32;
    }
    
}

void toLower(char A[]) {

    for (int i = 0; A[i] != '\0'; i++) {
        A[i] = A[i] + 32;
    }    

}

void toggleCase(char A[]) {

    for (int i = 0; A[i] != '\0'; i++) {
        if (A[i] >= 'A' && A[i] <= 'Z') {
            A[i] = A[i] + 32;
        } else if (A[i] >= 'a' && A[i] <= 'z') {
            A[i] = A[i] - 32;
        }
    }

}
```

Contributed by Nitin Ranganath

