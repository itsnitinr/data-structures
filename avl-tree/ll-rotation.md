# LL Rotation

**LL rotation is used when there is an imbalance due to the left child of the left child of a node.** 

### Procedure :

* Let ptr be the parent node. ptrL is the left child of parent node and ptrLR is the right child of left child of parent node.
* Make ptr the right child of ptrL such that ptrL becomes the parent node.
* Make ptrLR the left child of ptr. 
* Change the height of ptr and ptrL.
* Change root if necessary.

```c
struct Node *LLRotation(struct Node *ptr) {

	// Pointers to the left child and its right child
	struct Node *ptrL = ptr -> left;
	struct Node *ptrLR = ptrL -> right;

	// Make ptr the right child of ptrL
	ptrL -> right = ptr;
	ptr -> left = ptrLR;
	// Set the new heights
	ptr -> height = nodeHeight(ptr);
	ptrL -> height = nodeHeight(ptrLl);

	// Change root if required
	if (ptr == root) 
		root = ptrL;

	return ptrL;

}
```

