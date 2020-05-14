# Searching in a BST

### Procedure :

* Start from the root node.
* Compare the data in each node with the key. If it matches, return pointer to that node.
* If the key is lesser than the data in the node, move pointer to the left child.
* If the key is greater than the data in the node,  move pointer to the right child.
* If pointer becomes null, it means the we have reached the end of the tree and the element was not found. Therefore, return NULL.

### Iterative Function :

```c
struct Node *BSTsearch(struct Node *ptr, int key) {

    while (ptr != NULL) {
        if (key == ptr -> data) {
            return ptr;
        } else if (key < ptr -> data) {
            ptr = ptr -> left;
        } else {
            ptr = ptr -> right;
        }
    }
    return NULL;
    
}
```

### Recursive Function :

```c
struct Node *BSTsearch(struct Node *ptr, int key) {

    if (ptr == NULL) {
        return NULL;
    }
    
    if (key == ptr -> data) {
        return ptr;
    } else if (key < ptr -> data) {
        return BSTsearch(ptr -> left, key);
    } else {
        return BSTsearch(ptr -> right, key);
    }

}
```

**Time Complexity : O\(log n\)**

Contributed by Nitin Ranganath

