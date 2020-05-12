---
description: 'Implementation of append, insert, delete and display function in an array.'
---

# Array ADT

### Creating a Structure for Array 

```c
struct Array {
    int A[20];
    int length;
    int size;
}
```

The following Array structure has three key elements to it: 

* The actual array
* An integer to store the length of the array \(No. of elements present\)
* An integer to store the size of an the array \(Maximum capacity\)

### Appending to the End

For appending an element to the end of an array, we need to first increment the length of the array and then store the desired value in the last index of array. This can be implemented using the following C code :

```c
void append(struct Array *arr, int value) {

    // Check if there is enough space to append
    if (arr -> length < arr -> size) {
        // Set desired value the last index and increment length
        arr -> A[length++] = value;
    }
    
}
```

### Inserting at a Specific Index

To insert an element at a particular index in the array, we must check if there's enough space in the array and then shift all the elements to the right of desired index by 1. This creates a space for the element to be inserted at the desired index. Function for the same : 

```c
void insert(struct Array *arr, int index, int value) {
    
    // Check if index is valid
    if (index >= 0 && index < arr -> length) {
        // Shift elements to the right 
        for (int i = 0; i > index; i++) {
            arr -> A[i] = arr -> A[i-1];
        }
        // Set the value at desired index
        arr -> A[index] = value;
        // Increment the length
        arr -> length++;
    }
    
}
```

### Deleting from Specific Index

In this operating, the index of the element which needs to be deleted will be passed along with the array. To perform this operation, all the elements which are present after the index from which an element was deleted should be shifted left by 1 and length of array must be decremented.

```c
void delete(struct Array *arr, int index) {

    // Check if index is valid or not
    if (index >= 0 && index < arr -> length) {
        // Shift elements to the left
        for (int i = index; i < arr -> length - 1; i++) {
            arr -> A[i] = arr -> A[i+1];
        }
        arr -> length--;
    }

}
```

Contributed by Nitin Ranganath

