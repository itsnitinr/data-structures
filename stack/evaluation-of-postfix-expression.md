---
description: Procedure to evaluate a postfix expression using stack.
---

# Evaluation of Postfix Expression

### Procedure :

* Iterate through each character of the given postfix expression.
* If the character is an operand \(0 to 9\), push it to stack after **properly typecasting into integer value from char value by subtracting 48**.
* If the character is an operator, pop 2 items from the stack. The element to the popped will be num2 and the next element will be num1.
* Evaluate the operation using switch case.
* Push the result of evaluation to stack.
* The result will be at stack top after the whole process.

### C Program :

```c
int isOperand(char);

// Main function
int main() {

    char postfix[30];
    int stack[30];
    int num1, num2, res, i, top=-1;

    printf("Enter a postfix expression : \n");
    scanf("%s",postfix);

    // Iterate through each character of postfix expression
    for(i=0;postfix[i]!='\0';i++) {

        // If character is an operand, push it to stack
        if(isOperand(postfix[i])==1) {
            top++;
            stack[top] = (int)(postfix[i]-48);
        }

        // If character is an operator, pop 2 items from stack and perform operation
        else {
            
            // Popping two items from stack
            num2 = stack[top];
            top--;
            num1 = stack[top];
            top--;

            // Switch case to choose operation
            switch(postfix[i]) {

                case '+' : res = num1+num2;
                break;

                case '-' : res = num1-num2;
                break;

                case '*' : res = num1*num2;
                break;

                case '/' : res= num1/num2;
                break;

            }

            // Add result to stack top
            top++;
            stack[top] = res;

        }
    }

    // Getting result
    printf("Answer of expression : %d\n",stack[top]);
    return 0;

}

// isOperand function
int isOperand(char x) {

    if(x>='0' && x<='9') {
        return 1;
    }
    else {
        return 0;
    }

}
```

Contributed by Nitin Ranganath

