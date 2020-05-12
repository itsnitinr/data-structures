---
description: Procedure to display all the nodes in a circular linked list.
---

# Displaying the Nodes

### Iterative Method :

```c
void display(struct node *ptr) {

    // Use a do while loop
    do {
        printf("%d\t", ptr -> data);
        ptr = ptr -> next;
    } 
    while (ptr != head);

}
```

### Recursive Method :

```c
void display(struct node *ptr) {

    // A flag variable to check if head is reached second time
    static int flag = 0;
    
    if (ptr != head || flag = 0) {
        printf("%d\t", ptr -> data);
        display(ptr -> head);
    }
    // Make flag 0 again as it is static
    flag = 0;

}
```

Contributed by Nitin Ranganath

