# Duplicates in a String

```c
void findDuplicates(char a[]) {

    // Considering all characters to be lowercase
    // Range : 97 to 122 => Consider 97 as 0 and 122 as 25

    // Hash array
    int h[26] = {0};

    // Store count of each alphabet in hash array
    for (int i = 0; a[i] != '\0'; i++) {
        h[a[i] - 97]++;
    }

    // Displaying duplicates
    for (int i = 0; i < 26; i++) {
        if (h[i] > 1) {
            printf("Duplicate found : %c\n", i+97);
        }
    } 
    
}
```

Contributed by Nitin Ranganath

