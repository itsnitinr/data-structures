---
description: Implementation of queue using a linked list.
---

# Queue using Linked List

### Queue Node Structure :

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;
```

### Enqueue Operation :

```c
void enqueue(int data) {

    // Creating a new queue node
    struct Node *newNode;
    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode -> data = data;

    // If this node is the first node to be inserted
    if (front == NULL) {
        front = rear = newNode;
    }

    // If other nodes are already present
    else {
        rear -> next = newNode;
        rear = newNode;
    }
    
}
```

### Dequeue Operation :

```c
int dequeue() {

    // If queue is already empty
    if (front == NULL) {
        printf("Queue underflow\n");
        return -1;
    }

    else {
        // Pointers for node & data to be deleted
        struct Node *toDelete = front;
        int deletedData = front -> data;

        front = front -> next;
        free(toDelete);
        return deletedData;
    }
    
}
```

### Display Operation :

```c
void display() {

    // If queue is empty
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }

    struct Node *ptr = front;
    while (ptr != NULL) {
        printf("%d\t", ptr -> data);
        ptr = ptr -> next;
    }
    printf("\n");
    
}
```

Contributed by Nitin Ranganath

