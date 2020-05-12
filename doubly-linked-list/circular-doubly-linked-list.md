---
description: Basic operations for a circular doubly linked list.
---

# Circular Doubly Linked List

### Inserting a Node :

```c
void insert(struct node *ptr, int data, int pos) {

    // Creating a node
    struct node *newNode;
    newNode = (struct node *)malloc(sizeof(struct node));
    newNode -> data = data;

    // If node needs to be inserted at first position
    if (pos == 1) {
        if (head == NULL) {
            // If linked list is empty
            head = newNode;
            head -> prev = head;
            head -> next = head;
        } else {
            // If other nodes are present
            newNode -> prev = head -> prev;
            newNode -> next = head;
            head -> prev = newNode;
            newNode -> prev -> next = newNode;
            head = newNode;
        }
    }

    // If node is to be inserted at any other position
    else {
        for (int i = 0; i < pos - 2; i++) {
            ptr = ptr -> next;
        }
        // Change the links
        newNode -> next = ptr -> next;
        newNode -> prev = ptr;
        ptr -> next -> prev = newNode;
        ptr -> next = newNode;
    }
    
}
```

### Deleting a Node :

```c
void delete(struct node *ptr, int pos) {

    // If the head node is to be deleted
    if (pos == 1) {
        head -> prev -> next = head -> next;
        head -> next -> prev = head -> prev;
        head = head -> next;
        free(ptr);
    } 
    
    else {
        // Traverse to the node to be deleted
        for (int i = 0; i < pos - 1; i++) {
            ptr = ptr -> next;
        }
        // Change the links
        ptr -> prev -> next = ptr -> next;
        ptr -> next -> prev = ptr -> prev;
        //  Deallocate the memory
        free(ptr);
    }
    
}
```

### Displaying the Nodes :

```c
void display(struct node *ptr) {

    // If linked list is empty
    if (ptr == NULL) {
        printf("Linked list is empty\n");
        return;
    }
    
    do {
        printf("%d\t", ptr -> data);
        ptr = ptr -> next;
    }
    while (ptr != head);
    printf("\n");
    
}
```

Contributed by Nitin Ranganath

