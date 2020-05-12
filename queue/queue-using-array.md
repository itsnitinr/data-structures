---
description: Implementation of queue using arrays and its functions.
---

# Queue using Array

### Queue Structure :

```c
struct Queue {
    int size;
    int front;
    int rear;
    int *data;
};
```

### Creating a Queue Dynamically :

```c
struct Queue *createQueue(int size) {

    // Allocating memory for queue
    struct Queue *queue;
    queue = (struct Queue *)malloc(sizeof(struct Queue));
    
    // Set size, front and rear
    queue -> size = size;
    queue -> front = -1;
    queue -> rear = -1;
    
    // Allocating memory for array
    queue -> data = (int *)malloc(size * sizeof(int));
    
    return queue;

}
```

### Function to Check if Queue is Empty or Full :

```c
int isEmpty(struct Queue *queue) {
    return queue -> front == queue -> rear;
}

int isFull(struct Queue *queuevoid display(struct Queue *queue) {
  return queue -> rear == queue -> size - 1;
}
```

### En-queue Function :

```c
void enqueue(struct Queue *queue, int data) {

    if (isFull(queue)) {
        printf("Queue overflow !\n");
        return;
    }
    queue -> rear++;
    queue -> data[queue -> rear] = data;

}
```

### De-queue Function :

```c
int dequeue(struct Queue *queue) {

    if (isEmpty(queue)) {
        printf("Queue underflow !\n");
        return -1;
    }
    queue -> front++;
    int deletedValue = queue -> data[queue -> front];
    return deletedValue;

}
```

### Display Function :

```c
void display(struct Queue *queue) {

    for (int i = queue -> front + 1; i <= queue -> rear; i++) {
        printf("%d\t", queue -> data[i]);
    }
    printf("\n");

}
```

Contributed by Nitin Ranganath

