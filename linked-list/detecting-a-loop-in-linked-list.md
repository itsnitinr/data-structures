---
description: >-
  Procedure to check if a given list has a loop using Floyd's Cycle Finding
  Algorithm.
---

# Detecting a Loop in Linked List

### Procedure :

* Take two pointers : slow and fast
* Move the slow pointer by 1 node each time and fast pointer by 2 nodes each time.
* Perform the above step until either of the pointer become NULL or the next of fast becomes NULL. 
* Check if both the pointers are same. If so, the linked list has a loop. Else, it doesn't.

```c
int isLoop(struct node *ptr) {
    
    // Two pointers to check for loop
    struct node *slow = ptr;
    struct node *fast = ptr;
    
    while (slow && fast && fast -> next) {
        // Move slow by one step
        slow = slow -> next;
        // Move fast by two steps
        fast = fast -> next -> next;
        // Check if the pointers are same
        if (slow == fast) {
            return 1;
        }
    }
    return 0;

}
```

Contributed by Nitin Ranganath

