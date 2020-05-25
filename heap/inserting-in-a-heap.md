# Inserting in a Heap

### Some basics :

* Heap is stored in an array representation.
* Starting index is considered to be 1. Element at index 0 will be 0.
* For an element in **index i**, its left child will be at index **2i** and right child will be at **index 2i + 1**.
* For elements at index &gt; 2, its parent element will be at the floor value of **index /2**.

### Inserting in a Max Heap :

```c
void insertMaxHeap(int h[], int data, int index) {

    // Check if data is greater than parent
    while (index > 1 && data > h[index/2]) {
        h[index] = h[index/2];
        index = index/2;
    }
    h[index] = data;

}
```

### Inserting in a Min Heap :

```c
void insertMinHeap(int h[], int data, int index) {

    // Check if data is lesser than parent
    while (index > 1 && data < h[index/2]) {
        h[index] = h[index/2];
        index = index/2;
    }
    h[index] = data;

}
```

### Creating a Heap from Existing Array :

```c
void createHeap(int h[], int size) {

    for (int i = 2; i <= size; i++) {
        insertMaxHeap(h, h[i], i);
    }

}

// int h[5] = {0, 34, 12, 56, 4}; 
// Heap size is 4. Don't include first index.
// createHeap(h, 4);
```

