# Inserting in a BST

### Iterative Insert \(Using Tail Pointer\) :

```c
void insert(struct Node *ptr, int data) {

	// New node to be added
	struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
	newNode -> data = data;
	newNode -> left = newNode -> right = NULL;

	// Tail pointer 
	struct Node *parent = NULL;

	// If BST is empty, make new node as root node
	if (ptr == NULL) {
		root = newNode;
		return;
	}

	while (ptr != NULL) {
		
		// Move tail pointer to current node 
		parent = ptr;

		// Move current node to the next node
		if (ptr -> data == data) {
			// If the same data node is already present, free new node 
			free(newNode);
			return;
		}

		else if (data < ptr -> data)
			ptr = ptr -> left;
		else 
			ptr = ptr -> right;
	}

	if (data < parent -> data)
		parent -> left = newNode;
	else 
		parent -> right = newNode;

}
```

### Iterative Insert \(Without Using Tail Pointer\) :

```c
void insert(struct Node *ptr, int data) {

	// Creating a new node for new element
	struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
	newNode -> data = data;
	newNode -> left = newNode -> right = NULL;
	
	// If the BST is empty, make the new node as root
	if (ptr == NULL) {
		root = newNode;
		return;
	}

	while (ptr != NULL) {
		
		// If the element is already present in BST
		if (ptr -> data == data)
			return;

		else if (data < ptr -> data) {
			// If the left child is NULL, make new node as left child
			// Otherwise, go to the left child
			if (ptr -> left == NULL)
				ptr -> left = newNode;
			else
				ptr = ptr -> left;
		}

		else {			
			// If the right child is NULL, make new node as right child
			// Otherwise, go to the right child
			if (ptr -> right == NULL)
				ptr -> right = newNode;
			else
				ptr = ptr -> right;
		}
		
	}

}
```

### Recursive Insert :

```c
struct Node *insert(struct Node *ptr, int data) {

    // Create and return a new node when NULL
    if (ptr == NULL) {
        struct Node *newNode;
        newNode = (struct Node *)malloc(sizeof(struct Node));
        newNode -> left = newNode -> right = NULL;
        return newNode; 
    }
    
    // Insert at appropriate position
    if (data < ptr -> data) 
        ptr -> left = insert(ptr -> left, key);
    else if (data > ptr -> data)
        ptr -> right = insert(ptr -> right, key);
    return ptr;

}

// Call like this:
// root = insert(root, 10); <- Assign to root when calling first time
// insert(root, 20);
// insert(root, 30);
```

Contributed by Nitin Ranganath

