# Finding Sum of All Nodes

```c
int findSum(struct Node *ptr) {

    int x, y;
    
    if (ptr) {
        x = findHeight(ptr -> left);
        y = findHeight(ptr -> right);
        return x + y + ptr -> data;
    }
    return 0;

}
```

Contributed by Nitin Ranganath

