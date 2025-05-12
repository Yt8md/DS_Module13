# Ex5 Stack Operations
## DATE:24.2.25
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1. Increment top by 1.
2. Place x at stack[top].
3. Retrieve the element at stack[top]
4. Decrement top by 1
5. Return the retrieved element.
 
 

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Mathesh S
RegisterNumber:  212223230123
*/
#include <stdio.h>

#define SIZE 100

char stack[SIZE];
int top = -1;

// Push an element onto the stack
void push(char x) {
    if (top == SIZE - 1) {
        printf("Stack Overflow\n");
        return;
    }
    stack[++top] = x;
}

// Pop an element from the stack
char pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
        return -1;  // Error value
    }
    return stack[top--];
}






```

## Output:
![image](https://github.com/user-attachments/assets/2156017b-dda9-484c-9039-153359d18cc9)



## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
