---
description: Iterative and recursive approaches to reverse a linked list.
---

# Reversing a Linked List

### Reversing by Changing Node Data & Using an Array :

* Pass the pointer to head node and an array as parameters.
* Using a while loop, copy the data from each node to the array until the pointer becomes NULL.
* Set the pointer to head and decrement to index i by 1 to reach the last element of array.
* Overwrite the data in each node using a while loop and keep decrementing the index i until pointer becomes NULL.

```c
void reverse(struct node *ptr, int a[]) {
    
    // A variable to keep track of array index
    int i = 0;
    
    // Copy data from linked list to array
    while (ptr != NULL) {
        a[i] = ptr -> data;
        i++;
        ptr = ptr -> next;
    }
    
    // Set index to begin reverse procedure
    ptr = head;
    i--;
    
    // Copy data from array to linked list in reverse
    while (ptr != NULL) {
        ptr -> data = a[i];
        i--;
        ptr = ptr -> next;
    }
    
}
```

### Reversing using Sliding Pointers :

* Take two additional pointers, prev and next, and initialise them with NULL.
* Copy the next address of each node to the next pointer and then set the next  address of node to the prev pointer.
* Make current as next and prev as current in order to move forward. 
* Do this procedure until current becomes NULL.
* Set the head node as prev pointer.

```c
void reverse(struct node *ptr) {

    // Consider ptr to the pointer to current node
    struct node *prev = NULL;
    struct node *next = NULL;

    while (ptr != NULL) {
        // Store the address of next node
        next = ptr -> next;
        // Make the next of each node point to its previous
        ptr -> next = prev;
        // Move forward
        prev = ptr;
        ptr = next;
    }
    // Setting the value of head node
    head = prev;   
}
```

### Reversing by Recursion :

```c
void reverse(struct node *prev, struct node *curr) {

    if (curr != NULL) {
        reverse(curr, curr -> next);
        curr -> next = prev;        
    } else {
        head = prev;
    }

}

// Function call : reverse(NULL, head) 
```

Contributed by Nitin Ranganath

