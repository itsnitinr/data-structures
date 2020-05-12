---
description: Procedure to delete a node from any position in a linked list.
---

# Deleting a Node

### Deleting the Head Node :

```c
void deleteFirst(struct node *ptr) {

    first = ptr -> next;
    free(ptr);

}
```

### Deleting a Node from Any Index :

```c
void delete(struct node *ptr, int index) {

    // If node to be deleted is the head node
    if (index == 1) {
        head = ptr -> next;
        free(ptr);
    }
    
    // Deleting other nodes
    else {
        for (int i = 0; i < index - 2; i++) {
            ptr = ptr -> next;
        }
        // Find the node to be deleted
        struct node *toDelete = ptr -> next;
        // Replace the link
        ptr -> next = toDelete -> next;
        // Deallocate the memory
        free(toDelete);
    }

}
```

Contributed by Nitin Ranganath

