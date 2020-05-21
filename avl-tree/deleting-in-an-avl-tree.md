# Deleting in an AVL Tree

### Procedure :

* Perform the same steps as deleting in a binary search tree.
* After that, assign new height to the node.
* Check the balance factor of the node. 
* According to the balance of the node and it's left/right child, perform rotation in order to balance the balance the tree

```c
struct Node *deleteNode(struct Node *ptr , int key) {
  
 		// If there's no node to be deleted
	if (ptr == NULL) 
		return NULL;

	// If the node is a leaf node
	if (ptr -> left == NULL && ptr -> right == NULL) {
		// If it's the root node, make root NULL after deletion
		if (ptr == root) 
			root = NULL;
		// Free the memory
		free(ptr);
		return NULL;
	}

	// If value to be deleted is lesser, go to left subtree
	if (key < ptr -> data) 
		ptr -> left = deleteNode(ptr -> left, key);

	// If value to be deleted is greater, go to right subtree
	else if (key > ptr -> data)
		ptr -> right = deleteNode(ptr -> right, key);
	
	// Deleting the node once it's found
	else {
		// Delete from the subtree which has greater height
		if (nodeHeight(ptr -> left) > nodeHeight(ptr -> right)) {

			// Find the inorder predecessor for left subtree
			struct Node *inPre = inorderPredecessor(ptr -> left);
			ptr -> data  = inPre -> data;
			ptr -> left = deleteNode(ptr -> left, inPre -> data);
		
		} else {

			// Find the inorder successor for right subtree
			struct Node *inSuc = inorderSuccessor(ptr -> right);
			ptr -> data  = inSuc -> data;
			ptr -> right = deleteNode(ptr -> right, inSuc -> data);
		
		}
	}
 	
 	// Set new height
    ptr->height = nodeHeight(ptr);
 
 	// Rotate as per balance factor
    if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == 1)
    	return LLRotation(ptr);		//L 1 Rotation
    else if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> left)==-1)
    	return LRRotation(ptr);		//L -1 Rotation
    else if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> left) == 0)
    	return LLRotation(ptr);		//L 0 Rotation
    else if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> right) == 1)
    	return RRRotation(ptr);  	//R 1 Rotation
    else if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> right) == -1)
    	return RLRotation(ptr); 	//R-1 Rotation
    else if(balanceFactor(ptr) == 2 && balanceFactor(ptr -> right) == 0)
    	return RRRotation(ptr);  	//R 0 Rotation
 
    return ptr;

}
```

**Utility Functions :**

```c
// Node height function
int nodeHeight(struct Node *ptr) {
	
	int leftHeight, rightHeight;
	leftHeight = ptr && ptr -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && ptr -> right ? ptr -> right -> height : 0;
	return leftHeight > rightHeight ? leftHeight + 1 : rightHeight + 1;

}

// Balance factor function
int balanceFactor(struct Node *ptr) {

	int leftHeight, rightHeight;
	leftHeight = ptr && ptr -> left ? ptr -> left -> height : 0;
	rightHeight = ptr && ptr -> right ? ptr -> right -> height : 0;
	return leftHeight - rightHeight;

}

// LL Rotation
struct Node *LLRotation(struct Node *ptr) {

	struct Node *ptrL = ptr -> left;
	struct Node *ptrLR = ptrL -> right;

	ptrL -> right = ptr;
	ptr -> left = ptrLR;

	ptr -> height = nodeHeight(ptr);
	ptrL -> height = nodeHeight(ptr -> left);

	if (ptr == root) 
		root = ptrL;

	return ptrL;

}

// LR Rotation
struct Node *LRRotation(struct Node *ptr) {

	struct Node *ptrL = ptr -> left;
	struct Node *ptrLR = ptrL -> right;

	ptrL -> right = ptrLR -> left;
	ptr -> left = ptrLR -> right;
	ptrLR -> left = ptrL;
	ptrLR -> right = ptr;

	ptr -> height = nodeHeight(ptr);
	ptrL -> height = nodeHeight(ptrL);
	ptrLR -> height = nodeHeight(ptrLR);

	if (ptr == root)
		root = ptrLR;

	return ptrLR;

}

// RR Rotation
struct Node *RRRotation(struct Node *ptr) {
	
	struct Node *ptrR = ptr -> right;
	struct Node *ptrRL = ptrR -> left;

	ptrR -> left = ptr;
	ptr -> right = ptrRL;

	ptr -> height = nodeHeight(ptr);
	ptrR -> height = nodeHeight(ptr -> right);

	if (ptr == root) 
		root = ptrR;

	return ptrR;

}

// RL Rotation
struct Node *RLRotation(struct Node *ptr) {
	
	struct Node *ptrR = ptr -> right;
	struct Node *ptrRL = ptrR -> left;

	ptrR -> left = ptrRL -> right;
	ptr -> right = ptrRL -> left;
	ptrRL -> left = ptr;
	ptrRL -> right = ptrR;

	ptr -> height = nodeHeight(ptr);
	ptrR -> height = nodeHeight(ptrR);
	ptrRL -> height = nodeHeight(ptrRL);

	if (ptr == root)
		root = ptrRL;

	return ptrRL;

}
```

Contributed by Nitin Ranganath

