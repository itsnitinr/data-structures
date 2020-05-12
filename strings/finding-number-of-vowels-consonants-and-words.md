# Finding Number of Vowels, Consonants & Words

* Initialise vowel and consonant count with 0.
* Initialise word count with 1 as there will be a minimum of 1 word in each string.
* Use a for loop to check all characters.
* If it is an uppercase or lowercase vowels, increment vowel count.
* If not, check if the character lies in the uppercase and lowercase alphabet range. If so, increment consonant count.
* If not, check if the character is a space. If so, increment word count.

```c
void countAll(char a[]) {

    int vowels=0, consonants=0, words=1;

    for (int i = 0; a[i] != '\0'; i++) {
        if (a[i] == 'a' || a[i] == 'e' || a[i] == 'i' || a[i] == 'o' || a[i] == 'u' || a[i] == 'A' || a[i] == 'E' || a[i] == 'I' || a[i] == 'O' || a[i] == 'U') {
            vowels++;
        } else if ((a[i] >= 'A' && a[i] <= 'Z') || (a[i] >= 'a' && a[i] <= 'z')) {
            consonants++;
        } else if (a[i] == ' ') {
            words++;
        }
    }

    printf("Vowels: %i\tConsontants: %i\tWords: %i\n", vowels, consonants, words);
    
}
```

Contributed by Nitin Ranganath

