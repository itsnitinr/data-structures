# AVL Tree Rotations

### LL Rotation :

```c
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
```

### RR Rotation :

```c
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
```

### LR Rotation :

```c
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
```

### RL Rotation :

```c
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

