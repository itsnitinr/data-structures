---
description: Implementation of double ended queue using linked list
---

# Double Ended Queue

### Inserting from Front :

```c
void frontEnqueue(int data) {

    // Creating a queue node
    struct Node *newNode;
    newNode = (struct node *)malloc(sizeof(struct Node));
    newNode -> data = data;
    
    // If this node is the first node to be inserted
    if (front == NULL) {
        front = rear = newNode;
        newNode -> next = NULL;
    }
    
    else {
        // Make newNode as front node
        newNode -> next = front;
        front = newNode;
    }

}
```

### Inserting from Rear :

```c
void rearEnqueue(int data) {

    // Creating a queue node
    struct Node *newNode;
    newNode = (struct node *)malloc(sizeof(struct Node));
    newNode -> data = data;
    newNode -> next = NULL;
            
    // If this node is the first node to be inserted
    if (front == NULL) {
        front = rear = newNode;
    }
    
    else {
        rear -> next = newNode;
        newNode -> next = NULL
        rear = newNode;
    }

}
```

### Deleting from Front :

```c
int frontDequeue() {

    // If queue is empty
    if (front == NULL) {
        printf("Queue is empty\n");
        return -1;
    }
    
    else {
        // Pointer for node and data to be deleted
        struct node *toDelete = front;
        int deletedData = front -> data;
        front = front -> next;
        free(toDelete);
    }

}
```

### Deleting from Rear :

```c
int rearDequeue() {

    // If queue is empty
    if (front == NULL) {
        printf("Queue is empty\n");
        return -1;
    }
    
    else {
        // Reach rear node
        struct node *ptr = front;
        while (ptr -> next != rear) {
            ptr = ptr -> next;
        }
        // Delete rear node 
        struct node *toDelete = rear;
        int deletedData = rear -> data;
        free(rear);
        // Make previous node as rear
        rear = ptr;
        rear -> next = NULL;
    }

}
```

Contributed by Nitin Ranganath

