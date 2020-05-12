---
description: A program to check if the parenthesis are balanced in an equation.
---

# Balancing Parenthesis

### Procedure : 

* Iterate through the input equation character by character.
* If an opening bracket is found, push it to stack.
* If a closing bracket is found, pop from the stack and check if the popped bracket and the closing bracket match \(are of the same type\).
* If stack is empty and a closing bracket is found, the parenthesis are not balanced.
* If the stack is empty after iterating through all the characters, the parenthesis are balanced. Else, they are not balanced.

### C Function :

```c
// Function to check if pair is matching

int isMatchingPair(char a, char b) {

    if ( (a == '(' && b == ')') || (a == '[' && b == ']') || (a == '{' && b == '}') ) {
        return 1;
    } 
    return 0;

}

int isBalanced(char *equation) {

    // Creating a stack of max size equal to string length
    int len = strlen(equation);
    char stack[len];
    int top = -1;
    
    // Iterating through each character
    for (int i = 0; equation[i] != '\0'; i++) {
        // Push to stack if opening bracket
        if (equation[i] == '(' || equation[i] == '[' || equation[i] == '{') {
            top++;
            stack[top] = equation[i];
        } 
        // Pop from stack if closing bracket
        else if (equation[i] == ')' || equation[i] == ']' || equation[i] == '}') {
            char poppedBracket = stack[top];
            top--;
            // If pairs are not matching, return false.
            if (!isMatchingPair(poppedBracket, equation[i])) {
                return 0;
            }
        }
    }

    // If stack is empty, parenthesis are balanced.    
    if (top == -1) {
        return 1;
    }
    return 0;

}
```

Contributed by Nitin Ranganath

