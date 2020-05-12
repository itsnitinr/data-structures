---
description: >-
  Iterative and recursive implementation of linearly searching for an element in
  a linked list.
---

# Searching in a Node

### Iterative Method :

```c
struct node * search(struct node *ptr, int key) {

    while (ptr != NULL) {
        if (ptr -> data == key) {
            // Return address of node if found
            return ptr;
        }
        ptr = ptr -> next;
    }
    return NULL;

}
```

### Recursive Method :

```c
struct node * search(struct node *ptr, int key) {

    // Base condition
    if (ptr == NULL) {
        return NULL;
    } 
    
    // Recursive call
    if (ptr -> data == key) {
        return ptr;
    else {
        return search(ptr -> next, key);
    }
    
}
```

### Improving Using Move to Head Technique :

```c
struct node * search(struct node *ptr, int key) {

    // A pointer which will follow ptr
    struct node *prev = NULL;
    
    while (ptr != NULL) {
        if (p -> data == key) {
            // Move the found node to the start 
            prev -> next = ptr -> next;
            ptr -> next = head;
            head = ptr;
            return ptr;
        }
        prev = ptr;
        ptr = ptr -> next;
    }
    return NULL;

}
```

Contributed by Nitin Ranganath

