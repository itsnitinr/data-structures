# Deleting in a BST

### Procedure :

* Search recursively for the data to be deleted. 
* Call the function on the left subtree if the data to be deleted is less than current node's data.
* Call the function on the right subtree if the data to be deleted is greater than current node's data.
* Once the node is found, check the height of it's left and right subtree.
* If the height of left subtree is greater, find the inorder predecessor and replace the data in node to be deleted with inorder predecessor's data. Now, delete the inorder predecessor as it's a leaf node.
* If the height of right subtree is greater, find the inorder successor and replace the data in node to be deleted with inorder successor's data. Now, delete the inorder successor as it's a leaf node.
*  If the node to be deleted is a leaf node, check if it is the root node. If yes, make the root as NULL. Then, free the memory.

```c
struct Node *deleteNode(struct Node *ptr, int key) {

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
		if (height(ptr -> left) > height(ptr -> right)) {

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

	return ptr;

}
```

**Utility Functions :**

```c
int height(struct Node *ptr) {

	int x, y;

	if (ptr == NULL)
		return 0;

	x = height(ptr -> left);
	y = height(ptr -> right);
	
	return x > y ? x + 1 : y + 1;

}

struct Node *inorderPredecessor(struct Node *ptr) {

	// Find rightmost child of left subtree
	while (ptr && ptr -> right)
		ptr = ptr -> right;
	return ptr;

}

struct Node *inorderSuccessor(struct Node *ptr) {

	// Find leftmost child of right subtree
	while (ptr && ptr -> left)
		ptr = ptr -> left;
	return ptr;

}
```

Contributed by Nitin Ranganath

