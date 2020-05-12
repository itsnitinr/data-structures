---
description: Finding all the permutations of a string using backtracking and recursion.
---

# Permutations of a String

### Backtracking C Function :

```c
void permutate(char a[], int l, int r) {

    if (l==r) {
        // Print the string when indexes match
        printf("%s\n", a);
    } else {
        for (int i = l; i <= r; i++) {
            // Swap to get permutation
            swap(&a[l], &a[i]);
            // Recursive call
            permutate(a, l+1, r);
            // Backtrack
            swap(&a[l], &a[i]);
        }
    }

}

```

Contributed by Nitin Ranganath

