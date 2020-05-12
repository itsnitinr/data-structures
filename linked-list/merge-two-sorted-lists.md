---
description: Procedure to merge two sorted linked lists.
---

# Merge Two Sorted Lists

```c
void merge(struct node *first, struct node *second) {

    // A pointer to keep track of last node of merged list
    struct node *last;
    
    // First node of merged list
    if (first -> data < second -> data) {
        // Set head and tail of merged list
        third = last = first;
        // Move forward in first list
        first = first -> next;
    } else {
        // Set head and tail of merged list
        third = last = second;
        // Move forward in second list
        second = second -> next;
    }
    third -> next = NULL;
    
    // Remaining node of merged list
    while (first && second) {
        if(first -> data < second -> data) {
            // Next node will be first's node
            last -> next = first;
            // Update the last pointer
            last = first;
            first = first -> next;
        } else {
            // Next node will be second's node
            last -> next = second;
            // Update the last pointer
            last = second;
            second = second -> next;
        }
    }
    
    // Merging remaining elements of first list (if any)
    if (first) {
        last -> next = first;
    }
    
    // Merging remaining elements of second list (if any)
    if (second) {
        last -> next  = second;
    }

}
```

Contributed by Nitin Ranganath

