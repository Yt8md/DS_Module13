# Ex4 Evaluation of prefix expression
## DATE:24.2.25
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
Initialize an empty stack.

2.Traverse the prefix expression from right to left:

If the symbol is an operand (number):

Push it onto the stack.

If the symbol is an operator (+, -, *, /):

Pop two operands from the stack.

Apply the operator to the operands: result = op1 operator op2.

Push the result back onto the stack.

3.After the entire expression is processed, the stack will contain the final result at the top.

4.Print the result.  

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: Mathesh S
RegisterNumber:  212223230123
*/
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int ch)
{
	top++;
	s[top]=ch;
}

int pop()
{
	int ch;
	ch=s[top];
	top=top-1;
	return(ch);
}

void evalprefix(char prefix[50])
{
  	int a,b,c,i;
  	for(i=strlen(prefix)-1;i>=0;i--)
  	{
  	    if(prefix[i]=='+')
  	    {
  	        c=pop()+pop();
  	        push(c);
  	    }
  	    else if(prefix[i]=='*')
  	    {
  	        a=pop();
  	        b=pop();
  	        c=a*b;
  	        push(c);
  	    }
  	    else if(prefix[i]=='-')
  	    {
  	        a=pop();
  	        b=pop();
  	        c=a-b;
  	        push(c);
  	    }
  	    else if(prefix[i]=='/')
  	    {
  	        a=pop();
  	        b=pop();
  	        c=a/b;
  	        push(c);
  	    }
  	       
  	    else{
  	        push(prefix[i]-48);
  	    }
  	    
  	}
  	printf("%d",pop());
}

int  main()
{
  char prefix[200];
  scanf("%s",prefix);
  evalprefix(prefix);
	return 0;
}


```

## Output:

![c763d06a-2b53-45fd-a559-2289638a8fa1](https://github.com/user-attachments/assets/d9fbe687-f590-4ef3-bf72-1415107c35c9)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
