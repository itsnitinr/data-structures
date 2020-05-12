---
description: Procedure to check if a linked list is sorted or not.
---

# Checking if List is Sorted

### Procedure :

* Check if only one node is present. If so, return true.
* Else, traverse through the list and check if the data of current node is greater than the data in the next node. If so, return false.
* Return true if while loop is completely executed without returning false.

```c
int isSorted(struct node *ptr) {

    // If only one node is present, it is sorted
    if (ptr -> next == NULL) {
        return 1;
    }

    else {
        // Check until last node is reached
        while (ptr -> next != NULL) {
            // If data of previous node is greater 
            if (ptr -> data > ptr -> next -> data) {
                return 0;
            }
            ptr = ptr -> next;
        }
        return 1;
    }
    
}
```

Contributed by Nitin Ranganath

