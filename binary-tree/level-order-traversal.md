# Level Order Traversal

**The below function requires a queue data structure of type pointer to Node to be created and initialised.** 

```c
void levelOrder(struct Node *ptr) {

    // Queue structure to store pointer
    struct Queue q;
    
    // Print the root node as it is on the topmost level
    printf("%d\t", ptr -> data);
    // Enqueue root node to the queue
    enqueue(&q, ptr);
    
    while (!isEmpty(q)) {
        // Obtain root of subtree
        ptr = dequeue(&q);
        // Print & enqueue the left child of next level if present
        if (ptr -> left) {
            printf("%d\t", ptr -> left -> data);
            enqueue(&q, ptr -> left);
        }
        // Print & enqueue the left child of next level if present
        if (ptr -> right) {
            printf("%d\t", ptr -> right -> data);
            enqueue(&q, ptr -> right); 
        }
    }

}
```

Contributed by Nitin Ranganath

