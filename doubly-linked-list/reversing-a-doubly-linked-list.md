---
description: Procedure to reverse a doubly linear linked list.
---

# Reversing a Doubly Linked List

```c
void reverse(struct node *ptr) {

    // Temporary pointer for swapping
    struct node *temp;
    
    while (ptr != NULL) {
        // Swapping the links
        temp = ptr -> next;
        ptr -> next = ptr -> prev;
        ptr -> prev = temp;
        // Moving forward
        ptr = ptr -> prev;
        // Condition to set head node
        if (ptr != NULL && ptr -> next == NULL) {
            head = ptr;
        }
    }
    
}
```

Contributed by Nitin Ranganath

