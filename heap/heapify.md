# Heapify

### Max Heapify :

```c
void maxHeapify(int h[], int index, int size) {

    // Set largest as parent and set children
    int left = 2 * index;
    int right = 2 * index + 1;
    int largest = index;
    
    // If left child is greater, make largest point to it
    if (left <= size && h[left] > h[largest])
        largest = left;
    
    // If right child is greater, make largest point to it
    if (right <= size && h[right] > h[largest])
        largest = right;
        
    // If largest is not parent, swap it with passed index
    if (largest != index) {
        int temp = h[index];
        h[index] = h[largest];
        h[largest] = temp;
        maxHeapify(h, largest, size);
    }
    return;

}
```

### Min Heapify :

```c
void minHeapify(int h[], int index, int size) {

    // Set smallest as parent and set children
    int left = 2 * index;
    int right = 2 * index + 1;
    int smallest = index;
    
    // If left child is smaller, make smallest point to it
    if (left <= size && h[left] < h[smallest])
        smallest = left;
    
    // If right child is smaller, make smallest point to it
    if (right <= size && h[right] < h[smallest])
        smallest = right;
        
    // If smallest is not parent, swap it with passed index
    if (smallest != index) {
        int temp = h[index];
        h[index] = h[smallest];
        h[smallest] = temp;
        minHeapify(h, smallest, size);
    }
    return;

}
```

**Note:** To build a max heap or min heap, run the function n/2 times . Like this :

```c
for (int i = size/2; i >= 1; i--) {
    maxHeapify(heap,i,size);
}
```

