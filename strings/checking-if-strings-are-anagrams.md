---
description: >-
  Strings which are composed of the same alphabets and their frequency are known
  as anagrams of each other.
---

# Checking if Strings are Anagrams

### Procedure :

* Take the two strings as input
* Create an hash array of size 26 and initialise it with 0.
* For each character the first string, **increment** the corresponding index in the hash array.
* For each character in the second string, **decrement** the corresponding index in the hash array.
* Loop through the hash array. If any of the element is not 0, return false. Else, return true.

### C Function :

```c
int checkAnagram(char a[], char b[]) {

    // Create and initialise hash array with 0.
    int h[26] = {0};

    // Increment for first string
    for (int i = 0; a[i] != '\0'; i++) {
        h[a[i]-97]++;
    }

    // Decrement for second string
    for (int i = 0; b[i] != '\0'; i++) {
        h[b[i]-97]--;
    }
    
    // If any element is not zero, it is not an anagram.
    for (int i = 0; i < 26; i++) {
        if (h[i] != 0) {
            return 0;
        }
    }
    return 1;
       
}
```

Contributed by Nitin Ranganath

