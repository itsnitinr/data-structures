---
description: Procedure to insert in node in doubly linear linked list.
---

# Inserting a Node

```c
void insert(struct node *ptr, int data, int pos) {

    // Creating a new node
    struct node *newNode;
    newNode = (struct node *)malloc(sizeof(struct node));
    newNode -> data = data;

    // If node is to be inserted at first position
    if (pos == 1) {
        if (head == NULL) {
            newNode -> prev = NULL;
            newNode -> next = NULL;
            head = newNode;
        } else {
            newNode -> prev = NULL;
            newNode -> next = head;
            head = newNode;
        }
    }

    // If node is to be inserted in any other position
    else {
        for (int i = 0; i < pos - 2; i++) {
            ptr = ptr -> next;
        }
        newNode -> next = ptr -> next;
        newNode -> prev = ptr;
        // Check if next node is available
        if (ptr -> next) {
            ptr -> next -> prev = newNode;
        }
        ptr -> next = newNode;
    }
    

```

Contributed by Nitin Ranganath

