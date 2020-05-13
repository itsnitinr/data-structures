# Counting Nodes in a Binary Tree

### Count All Nodes in Binary Tree :

```c
int countAllNodes(struct Node *ptr) {

    // Variables to obtain nodes is left and right subtree
    int leftNodes, rightNodes;
    
    if (ptr) {
        leftNodes = countAllNodes(ptr -> left);
        rightNodes = countAllNodes(ptr -> right);
        return leftNodes + rightNodes + 1;
    }
    return 0;

}
```

### Count Nodes Having Both Children \(Degree 2\) :

```c
int countTwoChildren(struct Node *ptr) {

    // Variables to obtain nodes is left and right subtree
    int leftNodes, rightNodes;
    
    if (ptr) {
        leftNodes = countTwoChildren(ptr -> left);
        rightNodes = countTwoChildren(ptr -> right);
        // Check if both children are present
        if (ptr -> left && ptr -> right) {
            return leftNodes + rightNodes + 1;
        } else {
            return leftNodes + rightNodes;
        }
    }
    return 0;

}
```

### Count Nodes Having One or More Children \(Degree 1 or 2\) :

```c
int countOneOrMore(struct Node *ptr) {

    // Variables to obtain nodes is left and right subtree
    int leftNodes, rightNodes;
    
    if (ptr) {
        leftNodes = countOneOrMore(ptr -> left);
        rightNodes = countOneOrMore(ptr -> right);
        // Check if atleast one child is present
        if (ptr -> left || ptr -> right) {
            return leftNodes + rightNodes + 1;
        } else {
            return leftNodes + rightNodes;
        }
    }
    return 0;

}
```

### Count Nodes Having Exactly One Child \(Degree 1\) :

```c
int countOneChild(struct Node *ptr) {

    // Variables to obtain nodes is left and right subtree
    int leftNodes, rightNodes;
    
    if (ptr) {
        leftNodes = countOneChild(ptr -> left);
        rightNodes = countOneChild(ptr -> right);
        // Perform XOR operation to check if only child is present
        if (ptr -> left ^ ptr -> right) {
            return leftNodes + rightNodes + 1;
        } else {
            return leftNodes + rightNodes;
        }
    }
    return 0;

}
```

### Count Leaf Nodes \(Degree 0\) :

```c
int countLeafNodes(struct Node *ptr) {

    // Variables to obtain nodes is left and right subtree
    int leftNodes, rightNodes;
    
    if (ptr) {
        leftNodes = countLeafNodes(ptr -> left);
        rightNodes = countLeafNodes(ptr -> right);
        // Check if both children are NULL
        if (!(ptr -> left) && !(ptr -> right)) {
            return leftNodes + rightNodes + 1;
        } else {
            return leftNodes + rightNodes;
        }
    }
    return 0;

}
```

### Alternative Way of Counting \(Without Variables\) :

```c
int count(struct Node *ptr) {

    if (ptr == NULL) {
        return 0;
    } 
    return count(ptr -> left) + count(ptr -> right) + 1;

}
```

Following the same style for all the other conditions.

Contributed by Nitin Ranganath

