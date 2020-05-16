# Inserting in an AVL Tree

### Procedure :

* Use the same procedure as used to insert a node in BST.
* However, set the height of the node after linking it with the parent node.
* The height will be the maximum of height of its left subtree and its right subtree.
* After that, find the balance factor and perform necessary rotation as required. 

```c
struct Node *insert(struct Node *ptr, int data) {

    // Create and return a new node when NULL
    if (ptr == NULL) {
        struct Node *newNode;
        newNode = (struct Node *)malloc(sizeof(struct Node));
        newNode -> left = newNode -> right = NULL;
        newNode -> height = 1;
        return newNode; 
    }
    
    // Insert at appropriate position
    if (data < ptr -> data) 
        ptr -> left = insert(ptr -> left, key);
    else if (data > ptr -> data)
        ptr -> right = insert(ptr -> right, key);
    
    // Set height of the node
    ptr -> height = nodeHeight(ptr);
    
    // Rotate as per the balance factor
    if (balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == 1) 
    	LLRotation(ptr);
    else if (balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == -1)
    	LRRotation(ptr);
    else if (balanceFactor(ptr) == -2 && balanceFactor(ptr -> left) == -1)
    	RRRotation(ptr);
    else if (balanceFactor(ptr) == -2 && balanceFactor(ptr -> left) == 1)
    	RLRotation(ptr);

    return ptr;

}
```

**Utility Functions :**

```c
int nodeHeight(struct Noded *ptr) {

	// Two variables for height of left subtree and right subtree
	int leftHeight, rightHeight;

	leftHeight = ptr && p -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && p -> right ? ptr -> right -> height : 0;

	return leftHeight > rightHeight ? leftHeight + 1 : rightHeight + 1;

}

int balanceFactor(struct Node *ptr) {

	// Two variables for height of left subtree and right subtree
	int leftHeight, rightHeight;

	leftHeight = ptr && p -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && p -> right ? ptr -> right -> height : 0;

	return leftHeight - rightHeight;

}
```

