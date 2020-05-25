# Deleting in a Heap

### Procedure :

* Copy the last element to root i.e index 1.
* Shift the root element to last element of heap.
* Set i as 1 \(root\) and j as 2\*i \(left child of root\).
* Perform the following until j &lt; size - 1.
* Find which of the child is greater.
* Set j to point on that child.
* If the child element \(j\) is greater than parent element \(i\), swap them.
* Set i as j and j as 2\*j after each iteration. 

```c
int deleteFromHeap(int h[], int size) {

	// Copy last element to root and first element to last place
	int lastElement = h[size];
	int firstElement = h[1];
	h[1] = lastElement;
	h[size] = firstElement;

	// Keep i at root and j at left child of root initially
	int i = 1, j = 2*i;

	while(j < size-1) {

		// Find out if left child is greater or right child
		if (h[j+1] > h[j]) 
			j = j + 1;
	
		// If child is greater than parent, interchange
		if (h[j] > h[i]) {
			int temp = h[i];
			h[i] = h[j];
			h[j] = temp;
			// Set i to j and j to left child of j
			i = j;
			j = 2*j;
		} else {
			break;
		}
	}
	return firstElement;

}
```

**By calling the same function n times, heap sort can be implemented.**

