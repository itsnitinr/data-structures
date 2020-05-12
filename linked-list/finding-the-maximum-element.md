---
description: Iterative and recursive way of finding the maximum among all the node's data.
---

# Finding the Maximum Element

### Iterative Method :

```c
int maximum(struct node *ptr) {

    // Variable to keep track of maximum element
    // Initialise with INT_MIN 
    int max = INT_MIN;
    
    while (ptr != NULL) {
        // Change max value is current data is greater 
        if (ptr -> data > max) {
            max = ptr -> data;
        }
        ptr = ptr -> next;
    }
    return max;
    
}
```

### Recursive Method :

```c
int maximum(struct node *ptr) {

    int max;
    
    if (ptr == NULL) {
        return INT_MIN;
    }
    max = maximum(p -> next);
    return max > p -> data ? max : p -> data;

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

