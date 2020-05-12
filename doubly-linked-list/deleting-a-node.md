---
description: Procedure to delete a node at a given index in a doubly linear linked list.
---

# Deleting a Node

```c
void delete(struct node *ptr, int pos) {

    // If first node is to be deleted
    if (pos == 1) {
        head = head -> next;
        if (head) {
            head -> prev = NULL;
        }
        free(ptr);
    }

    // Deleting any other node
    else {
        // Reach the node to be deleted
        for (int i = 0; i < pos - 1; i++) {
            ptr = ptr -> next;
        }
        // Modify the links
        ptr -> prev -> next = ptr -> next;
        if (ptr -> next) {
            ptr -> next -> prev = ptr -> prev;
        }
        // Deallocate the memory
        free(ptr);
    }
    
}
```

Contributed by Nitin Ranganath

