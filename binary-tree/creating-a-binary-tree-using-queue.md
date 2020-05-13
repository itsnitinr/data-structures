# Creating a Binary Tree using Queue

**Note : The below code assumes that a queue of type pointer to Node is already created and initialised.** 

```c
struct Node {
    int data;
    struct Node *left;
    struct Node *right;
}

struct Node *root = NULL;

void createTree(int noOfNodes) {

    // Pointer to keep track of current node and for new nodes
    struct Node *ptr, *newNode;
    int data;
    
    // A queue to store addresses of each node
    struct Queue q;
    create(&q, noOfNodes);
    
    // Create the root node and make its child NULL by default
    printf("Enter the value of root\n");
    scanf("%d", &data);
    root = (struct Node *)malloc(sizeof(struct Node));
    root -> data = data;
    root -> left = root -> right = NULL;
    // Enqueue the root to queue
    
    // Repeat until no node is to be inserted further
    while (isEmpty(q)) {
        
        // Get address of current node
        ptr = dequque(&q);
        
        // Inserting left child node
        printf("Enter the left child of %d:\n", ptr -> data);
        scanf("%d", &data);
        if (data != -1) {
            newNode = (struct Node *)malloc(sizeof(struct Node));
            newNode -> data = data;
            newNode -> left = newNode -> right = NULL;
            ptr -> left = newNode;
        }
        
        // Inserting right child node
        printf("Enter the right child of %d:\n", ptr -> data);
        scanf("%d", &data);
        if (data != -1) {
            newNode = (struct Node *)malloc(sizeof(struct Node));
            newNode -> data = data;
            newNode -> left = newNode -> right = NULL;
            ptr -> right = newNode;
        }
    }

}
```

Contributed by Nitin Ranganath

