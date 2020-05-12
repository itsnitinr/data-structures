---
description: >-
  Iterative and recursive way of finding the sum of data of all the nodes in a
  linked list.
---

# Sum of all Nodes

### Iterative Method :

```c
int sum(struct node *ptr) {

    // A variable to keep track of sum
    int sum = 0;
    
    // Iterate till ptr becomes NULL
    while (ptr != NULL) {
        sum += ptr -> data;
        ptr = ptr -> next;
    }
    return sum;
    
}
```

### Recursive Method :

```c
int sum(struct node *ptr) {

    // Base condition for termination
    if (p == NULL) {
        return 0;
    }
    
    // Recursive call
    else {
        return sum(ptr -> next) + p -> data;
    }

}
```

### Time and Space Complexity :

{% tabs %}
{% tab title="Iterative" %}
Time complexity : **O\(n\)**  
Space complexity : **O\(n\)**
{% endtab %}

{% tab title="Recursive" %}
Time complexity : **O\(n\)**  
Space complexity : **O\(1\)**
{% endtab %}
{% endtabs %}

Contributed by Nitin Ranganath

