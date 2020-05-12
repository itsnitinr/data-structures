---
description: Implementation of a stack using linked list and its functions.
---

# Stack Using Linked List

### Stack Node Structure :

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *top = NULL;
```

### Function to Check if Stack is Empty :

```c
int isEmpty() {
    return top == NULL;
} 
```

### Stack Push Function :

```c
void push(int data) {

    // Creating a new stack node
    struct Node *newNode;
    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode -> data = data;
    
    // Set the next to point to current top
    newNode -> next = top;
    
    // Update top
    top = newNode;

}
```

### Stack Pop Function :

```c
int pop() {

    if (isEmpty()) {
        printf("Stack underflow !\n");
        return -1;
    }
    
    struct Node *toDelete = top;
    int poppedValue = top -> data;
    top = top -> next;
    
    free(toDelete);
    return poppedValue;

}
```

### Stack Peek Function :

```c
int peek() {
    return top -> data;
}
```

### Stack Display Function :

```c
void display() {

    if (isEmpty()) {
        printf("Stack is empty\n");
        return;
    }
    
    struct Node *ptr = top;
    while (ptr != NULL) {
        printf("%d\t", ptr -> data);
        ptr = ptr -> next;
    }
    printf("\n");

}
```

Contributed by Nitin Ranganath

