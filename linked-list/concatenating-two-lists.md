---
description: Procedure to concatenate two linked lists.
---

# Concatenating Two Lists

### Procedure :

* Take the head pointer of both linked lists as parameters.
* Traverse to the last node of first list.
* Make the next point to the first of second list.

```c
void concatenate(struct node *first, *second) (

    // Traversing to the last node of first list
    while (first -> next != NULL) {
        first = first -> next;
    }
    // Setting the next as first node of second list
    first -> next = second;
    
}
```

Contributed by Nitin Ranganath

