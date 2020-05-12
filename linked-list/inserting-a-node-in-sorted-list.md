---
description: Procedure to insert a new node in a sorted linked list.
---

# Inserting a Node in Sorted List

### Procedure :

* Create a new node and assign the  data to it.
* Check if the head node is NULL. If it is, no nodes are present in the linked list  and the new node will be the head.
* Check if the head node's data is greater than the data to be inserted. If so, the new node will become the head node.
* If nodes are already present, reach the proper position by checking if the data of next node in each iteration is less than the data to be inserted.
* Once the position is reached, set the next of new node to be the next of current node.
* Finally, set next of current node to new node.

```c
void insert(struct node *ptr, int data) {

    // Creating a node
    struct node *newNode;
    newNode = (struct node *)malloc(sizeof(struct node));
    newNode -> data = data;

    // If there are no nodes or first node data is greater
    if (head == NULL || head -> data > data) {
        newNode -> next = head;
        head = newNode;        
    }
    
    // Inserting at correct position
    else {
        while (ptr -> next != NULL && ptr -> next -> data < data) {
           ptr = ptr -> next;
       }
       newNode -> next = ptr -> next;
       ptr -> next = newNode;
    }

}
```

Contributed by Nitin Ranganath

