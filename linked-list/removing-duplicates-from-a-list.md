---
description: Procedure to remove duplicate nodes from a linked list.
---

# Removing Duplicates from a List

### Procedure  :

* Traverse the list until the next node is not NULL.
* If the data of current node and next node is the same, change the next of current node to next of next node and delete the next node.
* Else, move the current node to next of current node.

```c
void removeDuplicates(struct node *ptr) {

    while (ptr -> next != NULL) {

        // If data of the two nodes are same
        if (ptr -> data == ptr -> next -> data) {
            // Pointer for the node to be deleted
            struct node *toDelete = ptr -> next;
            // Replace the links
            ptr -> next = toDelete -> next;
            // Deallocate the memory
            free(toDelete);
        }
        
        // IMPORTANT : Advance only if no deletion
         else {
            ptr = ptr -> next;
        }
        
    }
    
}
```

Contributed by Nitin Ranganath

