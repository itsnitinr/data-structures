---
description: Iterative and recursive method to print all the nodes in a linked list.
---

# Displaying the Nodes

### Iterative Method :

```c
void display(struct node *ptr) {
    
    // Checking if list is empty
    if (ptr == NULL) {
        printf("The list is empty\n");
    }
    // Iterate till the end otherwise
    else {
        while (ptr != NULL) {
            printf("%d\t", ptr -> data);
            ptr = ptr -> next;
        }
    }
    
}
```

### Recursive Method :

```c
void display(struct node *ptr) {

    if (ptr != NULL) {
        printf("%d\t", ptr -> data);
        display(ptr -> next);
    }

}
```

### Recursive & Reversed :

```c
void display(struct node *ptr) {

    if (ptr != NULL) {
        display(ptr -> next);
        printf("%d\t", ptr -> data);
    }

}
```

### Time and Space Complexity :

{% tabs %}
{% tab title="Iterative" %}
Time Complexity : **O\(n\)  
No extra space**
{% endtab %}

{% tab title="Recursive" %}
Time complexity : **O\(n\)  
Internal stack of size n+1 is used.**
{% endtab %}
{% endtabs %}

Contributed by Nitin Ranganath

