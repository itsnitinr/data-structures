# Inserting in an AVL Tree

### Procedure :

* Use the same method used for inserting in a BST.
* Set the height of new nodes to either 1 or 0. \(1 used in code below\)
* Calculate the height and balance factor of each node.
* If the balance factor is not -1, 0 or 1, the tree is imbalanced.
* Perform required rotation.

```c
struct Node *insert(struct Node *ptr, int data) {

	if (ptr == NULL) {
		// Create a new node and assign required values
		struct Node *newNode;
		newNode = (struct Node *)malloc(sizeof(struct Node));
		newNode -> data = data;
		newNode -> left = newNode -> right = NULL;
		newNode -> height = 1;
		return newNode;
	}

	if (data < ptr -> data) 
		ptr -> left = insert(ptr -> left, data);
	else if (data > ptr -> data)
		ptr -> right = insert(ptr -> right, data);

	// Assign height as the max height of left subtree and right subtree
	ptr -> height = nodeHeight(ptr);

	// Check balance factor and perform rotation
	if (balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == 1) 
		return LLRotation(ptr);
	else if (balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == -1)
		return LRRotation(ptr);
	else if (balanceFactor(ptr) == -2 && balanceFactor(ptr -> right) == 1)
		return RLRotation(ptr);
	else if (balanceFactor(ptr) == -2 && balanceFactor(ptr -> right) == -1)
		return RRRotation(ptr);

	return ptr;

}
```

**Utility Functions :**

```c
int nodeHeight(struct Node *ptr) {
	
	int leftHeight, rightHeight;
	leftHeight = ptr && ptr -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && ptr -> right ? ptr -> right -> height : 0;
	return leftHeight > rightHeight ? leftHeight + 1 : rightHeight + 1;

}

int balanceFactor(struct Node *ptr) {

	int leftHeight, rightHeight;
	leftHeight = ptr && ptr -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && ptr -> right ? ptr -> right -> height : 0;
	return leftHeight - rightHeight;

}
```

Contributed by Nitin Ranganath

