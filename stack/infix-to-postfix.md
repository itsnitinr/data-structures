---
description: Program to convert an infix expression to a postfix expression.
---

# Infix to Postfix

### C Program :

```c
int priority(char);
int isOperand(char);

// Main function
int main() {

    // Required variables
    char infix[30], postfix[30], stack[30];
    int i;
    int j = -1;     // Used for postfix array
    int top = -1;   // Used for stack

    // Scanning the expression
    printf("Enter the infix expression : \n");
    scanf("%s", infix);

    // Scanning each character one by one
    for (i = 0; infix[i] != '\0'; i++) {

        // If character is an operand, add to postfix expression
        if (isOperand(infix[i]) == 1) {
            j++;
            postfix[j] = infix[i];
        }

        // If character is an operator
        
        // If stack is empty
        else if (top == -1) {
            top++;
            stack[top] = infix[i];
        }

        // If closing bracket is encountered, pop from stack until opening bracket is at stack top
        else if (infix[i] == ')') {
            while (stack[top] != '(') {
                j++;
                postfix[j] = stack[top];
                top--;
            }
            top--;
        }

        // If scanned operator has higher priority than stack top operator, push it to stack
        else if (priority(infix[i]) > priority(stack[top])) {
            top++;
            stack[top] = infix[i];
        }

        // If scanned operator has lower priority than stack top operator, pop from stack until stack top has lower priority
        else if (priority(stack[top]) >= priority(infix[i])) {
            while (priority(stack[top]) >= priority(infix[i]) && top != -1 && stack[top] != '(') {
                j++;
                postfix[j] = stack[top];
                top--;
            }
            top++;
            stack[top] = infix[i];
        }
    }

    // Pop all remaning operators from stack until stack is empty
    while (top != -1) {
        j++;
        postfix[j] = stack[top];
        top--;
    }

    // Set postfix[j+1] as \0 
    postfix[j + 1] = '\0';

    // Output the postfix expression
    puts(postfix);
    return 0;

}

// Priority function
int priority(char x) {

    if (x == '*' || x == '/') {
        return 3;
    }
    else if (x == '+' || x == '-') {
        return 2;
    }
    else if (x == '(' || x == ')') {
        return 1;
    }
    else {
        return 0;
    }

}

// isOperand function
int isOperand(char x) {

    if ((x >= 'a' && x <= 'z') || (x >= 'A' && x <= 'Z') || (x >= 0 && x <= 9)) {
        return 1;
    }
    else {
        return 0;
    }

}
```

Contributed by Nitin Ranganath

