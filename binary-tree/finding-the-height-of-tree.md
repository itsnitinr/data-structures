# Finding the Height of Tree

```c
int findHeight(struct Node *ptr) {

    int x, y;
    
    if (ptr) {
        x = findHeight(ptr -> left);
        y = findHeight(ptr -> right);
        if (x > y) {
            return x + 1;
        }
        return y + 1;
    }
    return 0;

}
```

Contributed by Nitin Ranganath

