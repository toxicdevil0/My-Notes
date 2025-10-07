Stacks are implemented using Arrays, they are based on the **LIFO Concept** which abbreviates to **Last In First Out**, it's kinda like a stack of books where when you add a book it starts from bottom and then keep adding books on top of them, now if you want to access the first book you have to first remove all of the books at the top, or you can say that the book came last gets accessed first (the LIFO concept).

For Example-
![[Excalidraw/Drawing 2025-07-31 01.02.06.excalidraw]]
In Stack we use a variable "Top" that has the index of the top most element in the Stack is. `Top` starts at `-1` and increases as elements are pushed into the stack. `Max` is the array size, so the top can go up to `Max - 1`.
### Algorithm for Insertion into Stack -
	1. if (Top == Max - 1) then print "Stack is full" and exit.
	2. else 
		1. take input "item" to be added into the stack
		2. Top = Top + 1 [^1]
		3. Stack[Top] = item
	3. exit
### Algorithm for Deletion from Stack -
	1. if (Top == -1) then print "Stack is empty" and exit.
	2. else
		1. Top = Top - 1 [^2] 
	3. exit

### Algorithm for Traversal in Stack -
	1. if (Top == -1) then print "Stack is empty" and exit.
	2. else repeat 3rd step
	3. for i = Top to 0 print Stack[i]
	4. exit

Syntax for Stack in C
```C
#include<stdio.h>  
#include<stdlib.h>  
#define MAX 5  
  
int main(){  
    int top = -1;  
    int Stack[MAX];  
    int item, ch;  
  
    while(1){  
        printf("1. Push\n");  
        printf("2. Pop\n");  
        printf("3. Traverse\n");  
        printf("4. Exit\n");  
        printf("Enter Your Choice:");  
        scanf("%d", &ch);  
          
  
        switch(ch){  
        case 1: if(top == MAX - 1){  
            printf("Stack is full\n");  
        } else {  
            printf("Enter the Element:\n");  
            scanf("%d", &item);  
  
            top++;  
            Stack[top] = item;  
        }  
        break;  
          
        case 2: if (top == -1){  
            printf("Stack is Empty\n");  
        } else {  
            printf("Item deleted is %d\n",Stack[top]);  
            top--;  
        }  
        break;  
  
        case 3: if (top == -1){  
            printf("Stack is empty\n");  
        } else {  
            for(int i = top; i>= 0; i--){  
                printf("%d\n", Stack[i]);  
            }  
        }  
        break;  
        case 4:  
        exit(0);  
  
        default:  
        printf("Invalid choice");  
        break;  
    }  
}  
}
```


[^1]: The item gets added into the Top + 1 index until the Stack is full, Insertion is also known as .push() in some languages like Java and C++.
[^2]: The top item in the stack gets removed as we do Top - 1, which makes the top element garbage value for us. Deletion is also known as .pop() in some languages like Java and C++.

---
[[Data Structures and Algorithms]]