---
description: Procedure to insert a node at a given index in a circular linked list.
---

# Inserting a Node

```c
void insert(struct node *ptr, int data, int postition) {

    // Creating a new node and assigning data
    struct node *newNode;
    newNode = (struct node *)malloc(sizeof(struct node));
    newNode -> data = data; 

    // If node is to be inserted before head
    if (position == 1) {
        // Checking if list is empty
        if (head == NULL) {
            head = newNode;
            head -> next = head;
        } 
        // If a node already exists
        else {
            // Traverse to end of list
            while (ptr -> next != head) {
                ptr = ptr -> next;
            }
            ptr -> next = newNode;
            newNode -> next = head;
        }        
    }
    
    // If node is to be inserted in any other index
    else {
        for (int i = 0; i < postition - 2; i++) {
            ptr = ptr -> next;
        }
        newNode -> next = ptr -> next;
        ptr -> next = newNode;
    }

}
```

Contributed by Nitin Ranganath

