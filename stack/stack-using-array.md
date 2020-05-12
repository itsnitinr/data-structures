---
description: Complete implementation of a stack using array and its functions.
---

# Stack Using Array

### Stack Structure :

```c
struct Stack {
    int size;
    int top;
    int *data;
};
```

### Creating a Stack Dynamically :

```c
struct Stack *createStack(int size) {

    // Allocating memory for stack
    struct Stack *stack;
    stack = (struct Stack *)malloc(sizeof(struct Stack));

    // Setting size and top
    stack -> size = size;
    stack -> top = -1;

    // Allocating memory for data array
    stack -> data = (int *)malloc(size * sizeof(int));

    return stack;
    
}
```

### Function to Check if Stack is Empty or Full :

```c
int isFull(struct Stack *stack) {
    return stack -> top == stack -> size - 1;
}

int isEmpty(struct Stack *stack) {
    return stack -> top == -1;
}
```

### Stack Push Function :

```c
void push(struct Stack *stack, int data) {

    if (isFull(stack)) {
        printf("Stack overflow !\n");
        return;
    } else {
        stack -> top++;
        stack -> data[stack -> top] = data;
    }
    
}
```

### Stack Pop Function :

```c
int pop(struct Stack *stack) {

    if (isEmpty(stack)) {
        printf("Stack underflow !\n");
        return -1;
    } else {
        int poppedData = stack -> data[stack -> top];
        stack -> top--;
        return poppedData;
    }
    
}
```

### Stack Peek Function :

```c
int peek(struct Stack *stack) {

    if (isEmpty(stack)) {
        return -1;
    }
    return stack -> data[stack -> top];

}
```

### Stack Display Function :

```c
void display(struct Stack *stack) {

    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return;
    }
    
    for (int i = stack -> top; i >= 0; i--) {
        printf("%d\n", stack -> data[i]);
    }

}
```

Contributed by Nitin Ranganath

