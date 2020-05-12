---
description: An efficient way of checking if a string is a palindrome.
---

# Checking for Palindrome

### Procedure :

* Calculate the length of string if it isn't given as input.
* Initialise i with 0 and j with length - 1.
* Run a for loop till i &lt; j.
* Compare the i-th and j-th character in each iteration. 
* If it's not the same, return 0 \(false\).
* Else, return 1 \(true\) after the loop is completed.

### C Function :

```c
int checkPalindrome(char a[], int n) {

    int i = 0, j = n-1;
    for (i = 0, j = n-1; i < j; i++, j--) {
        if (a[i] != a[j]) {
            return 0;
        }
    }
    return 1;
    
}
```

Contributed by Nitin Ranganath

