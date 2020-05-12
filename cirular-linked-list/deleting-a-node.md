---
description: Procedure to remove a node from a given position in a circular linked list.
---

# Deleting a Node

```c
void delete(struct node *ptr, int position) {

    // If the current head node is to be deleted
    if (position == 1) {
        while (ptr -> next != head) {
            ptr = ptr -> next;
        }
        if (ptr == head) {
            free(head);
            head = NULL;
        } else {
            // Change the link
            ptr -> next = head -> next;
            // Deallocate the memory
            free(head);
            // Change head
            head = ptr -> next;
        }
    }
    
    // If node from any other position is to be deleted
    else {
        // Traverse to the required node
        for (int i = 0; i < position - 2; i++) {
            ptr = ptr -> next;
        }
        // Pointer for the node to be deleted
        struct node *toDelete;
        toDelete = ptr -> next;
        // Change the link
        ptr -> next = toDelete -> next;
        // Deallocate the memory
        free(toDelete);
    }

}
```

Contributed by Nitin Ranganath

