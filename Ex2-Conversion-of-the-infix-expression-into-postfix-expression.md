# Ex2 Conversion of the infix expression into postfix expression
## DATE:24.2.25
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
Step 1 : Initialize an empty stack to hold operators and set the top to -1.

Step 2 : Scan the input expression from left to right.

Step 3 : If operand, output it directly.

Step 4 : If '(, push it to stack; if ')', pop and output until '(' is found.

Step 5 : If operator, pop from stack and output while the top has higher or equal priority, then push the operator.

Step 6 : After scanning, pop and output all remaining operators from the stack.   

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Mathesh S
RegisterNumber:  212223230123
*/
#include<stdio.h>
#include<ctype.h>
char stack[100];
int top=-1;
void push(char x)
{
    stack[++top]=x;
}
char pop()
{
    if(top==-1)
    {
        return -1;
    }
    else
    {
        return stack[top--];
    }
}
int priority(char x)
{
    if(x=='(')
    return 0;
    else if((x=='&')||(x=='|'))
    return 1;
    else if((x=='+')||(x=='-'))
    return 2;
    else if((x=='*')||(x=='/')||(x=='%'))
    return 3;
    else if(x=='^')
    return 4;
    return -1;
}
void post(char *exp)
{
    char *e=exp;
    char x;
    while(*e!='\0')
    {
        if(isalnum(*e))
        {
            printf("%c ",*e);
        }
        else if(*e=='(')
        {
            push(*e);
        }
        else if(*e==')')
        {
            while((x=pop())!='(')
            {
                printf("%c ",x);
            }
        }
        else
        {
            while(priority(stack[top])>=priority(*e))
            {
                printf("%c ",pop());
            }
            push(*e);
        }
        e++;
    }
    while(top!=-1)
    {
        printf("%c ",pop());
    }
}
int main()
{
    char exp[100]="4*(2+5)*9";
    post(exp);
    return 0;  
}
```

## Output:

![3db30995-ba44-4a63-93de-21e3f24b09f0](https://github.com/user-attachments/assets/b0d69f1d-08ca-4627-ad33-33af739e0276)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
