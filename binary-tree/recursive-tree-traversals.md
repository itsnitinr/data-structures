# Recursive Tree Traversals

### Preorder Traversal :

```c
void preorderTraversal(struct Node *ptr) {

    if (ptr != NULL) {
        printf("%d\t", ptr -> data);
        preorderTraversal(ptr -> left);
        preorderTraversal(ptr -> right);
    }

}
```

### Inorder Traversal :

```c
void inorderTraversal(struct Node *ptr) {

    if (ptr != NULL) {
        inorderTraversal(ptr -> left);
        printf("%d\t", ptr -> data);
        inorderTraversal(ptr -> right);
    }

}
```

### Postorder Traversal :

```c
void postorderTraversal(struct Node *ptr) {

    if (ptr != NULL) {
        postorderTraversal(ptr -> left);
        postorderTraversal(ptr -> right);
        printf("%d\t", ptr -> data);
    }

}
```

**The time complexity of all 3 traversal methods in O\(n\).**

Contributed by Nitin Ranganath

