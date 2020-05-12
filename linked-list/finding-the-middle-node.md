---
description: Procedure to find the middle node of a singly linked list.
---

# Finding the Middle  Node

### First Method : Finding Length & Then Middle Element

* In the first scan of the linked list, find the length of linked list.
* Find the ceiling value of length/2.
* Traverse to the node having that index.

```c
int findMid(struct node *ptr) {

    int len = 0;
    // Finding the length of linked list
    while (ptr != NULL) {
        len++;
        ptr = ptr -> next;
    }
    // Find the middle position
    int mid = ceil(len/2);
    // Resetting ptr to head
    ptr  = head;
    // Return the middle element
    for (int i = 0; i < mid; i++) {
        ptr = ptr -> next;
    }
    return ptr -> data;

}
```

### Second Method : Using Two Pointers

* Take two pointers with initial value as the head address.
* Move pointer 2 two times in each iteration while it is not NULL.
* If pointer 2 is not NULL, move pointer 1 once.

```c
int findMid() {

    // Two pointers
    struct node *ptr1 = head;
    struct node *ptr2 = head;
    
    // Move until pointer 2 becomes NULL
    while (ptr2 != NULL) {
        // Move pointer 2 two times
        ptr2 = ptr2 -> next;
        // Don't move again if already NULL
        if (ptr2 != NULL) {
            ptr2 = ptr2 -> next;
        }
        // Move pointer 1 if pointer 2 is not NULL
        if (ptr2 != NULL) {
            ptr1 = ptr1 -> next;
        }
    }
    return ptr1 -> data;

}
```

Contributed by Nitin Ranganath

