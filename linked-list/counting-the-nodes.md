---
description: Iterative and recursive way of counting the number of nodes in a linked list.
---

# Counting the Nodes

### Iterative Method :

```c
int count(struct node *ptr) {

    // A variable to keep track of count
    int count = 0;

    // Iterate till ptr becomes NULL
    while (ptr != NULL) {
        count++;
        ptr = ptr -> next;
    }
    return count;

}
```

### Recursive Method :

```c
int count(struct node *ptr) {

    // Base condition for termination
    if (ptr == NULL) {
        return 0;
    }
    // Recursive call 
    else {
        return count(ptr -> next) + 1;
    }

}
```

### Time and Space Complexity :

{% tabs %}
{% tab title="Iterative" %}
Time complexity : **O\(n\)**  
Space complexity : **O\(1\)**
{% endtab %}

{% tab title="Recursive" %}
Time complexity : **O\(n\)**  
Space complexity : **O\(n\)**
{% endtab %}
{% endtabs %}

Contributed by Nitin Ranganath

