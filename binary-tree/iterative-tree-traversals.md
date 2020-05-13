# Iterative Tree Traversals

**The below functions assume that a stack of type pointer to Node is already created which supports push and pop operations.**

### Preorder Traversal :

```c
void preorderTraversal(struct Node *ptr) {

    // A stack to keep track of visited nodes
    struct Stack s;
    
    // Iterate until pointer is not NULL or stack is not empty
    while (ptr != NULL || !isEmpty(s)) {
        if (ptr) {
            printf("%d\t", ptr -> data);
            // Push current node address to stack
            push(&s, p);
            ptr = ptr -> left;
        } else {
            ptr = pop(&s);
            ptr = ptr -> right;
        }
    }

}
```

### Inorder Traversal :

```c
void inorderTraversal(struct Node *ptr) {

    // A stack to keep track of visited nodes
    struct Stack s;
    
    // Iterate until pointer is not NULL or stack is not empty
    while (ptr != NULL || !isEmpty(s)) {
        if (ptr) {
            // Push current node address to stack
            push(&s, p);
            ptr = ptr -> left;
        } else {
            ptr = pop(&s);
            printf("%d\t", ptr -> data);
            ptr = ptr -> right;
        }
    }

}
```

### Postorder Traversal :

```c
void postorderTraversal(struct Node *ptr) {

    // A stack to keep track of visited nodes
    struct Stack s;
    
    // Iterate until pointer is not NULL or stack is not empty
    while (ptr != NULL || !isEmpty(s)) {
        if (ptr) {
            // Push current node address to stack
            push(&s, p);
            ptr = ptr -> left;
        } else {
            ptr = pop(&s);
            ptr = ptr -> right;
            printf("%d\t", ptr -> data);
        }
    }

}

```

Contributed by Nitin Ranganath

