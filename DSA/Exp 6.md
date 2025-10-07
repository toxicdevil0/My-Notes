Experiment 6:  Repeat experiments 2, 3 & 4 with linked structure.

Implementation of Stack Using Linked List:
```C
#include <stdio.h>

#include <stdlib.h>

  

// Define the node structure

struct Node {

    int data;

    struct Node* next;

};

  

struct Node* top = NULL;

  

// Push operation

void push(int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->data = value;

    newNode->next = top;

    top = newNode;

    printf("%d pushed onto stack.\n", value);

}

  

// Pop operation

void pop() {

    if (top == NULL) {

        printf("Stack Underflow. Nothing to pop.\n");

        return;

    }

    struct Node* temp = top;

    printf("%d popped from stack.\n", top->data);

    top = top->next;

    free(temp);

}

  

// Display stack

void displayStack() {

    if (top == NULL) {

        printf("Stack is empty.\n");

        return;

    }

    struct Node* temp = top;

    printf("Stack elements (Top to Bottom): ");

    while (temp != NULL) {

        printf("%d -> ", temp->data);

        temp = temp->next;

    }

    printf("NULL\n");

}

  

// Main menu

int main() {

    int choice, value;

  

    while (1) {

        printf("\n--- STACK OPERATIONS USING LINKED LIST ---\n");

        printf("1. Push\n");

        printf("2. Pop\n");

        printf("3. Display Stack\n");

        printf("4. Exit\n");

        printf("Enter your choice: ");

        scanf("%d", &choice);

  

        switch (choice) {

        case 1:

            printf("Enter value to push: ");

            scanf("%d", &value);

            push(value);

            break;

        case 2:

            pop();

            break;

        case 3:

            displayStack();

            break;

        case 4:

            printf("Exiting program.\n");

            exit(0);

        default:

            printf("Invalid choice. Please try again.\n");

        }

    }

    return 0;

}
```
```C

Output:

--- STACK OPERATIONS USING LINKED LIST ---

1. Push

2. Pop

3. Display Stack

4. Exit

Enter your choice: <1>

Enter value to push: <10>

10 pushed onto stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <1>

Enter value to push: <20>

20 pushed onto stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <1>

Enter value to push: <30>

30 pushed onto stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Stack elements (Top to Bottom): 30 -> 20 -> 10 -> NULL

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

30 popped from stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Stack elements (Top to Bottom): 20 -> 10 -> NULL

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

20 popped from stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

10 popped from stack.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

Stack Underflow. Nothing to pop.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Stack is empty.

  

--- STACK OPERATIONS USING LINKED LIST ---

Enter your choice: <4>

Exiting program.
```

  
  

Implementation of queue using linked list:
```C
#include <stdio.h>

#include <stdlib.h>

  

// Node structure

struct Node {

    int data;

    struct Node* next;

};

  

struct Node* front = NULL;

struct Node* rear = NULL;

  

// Enqueue operation (insert at end)

void enqueue(int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->data = value;

    newNode->next = NULL;

  

    if (rear == NULL) {

        // Queue is empty

        front = rear = newNode;

    } else {

        rear->next = newNode;

        rear = newNode;

    }

    printf("%d enqueued to queue.\n", value);

}

  

// Dequeue operation (delete from front)

void dequeue() {

    if (front == NULL) {

        printf("Queue Underflow. Nothing to dequeue.\n");

        return;

    }

  

    struct Node* temp = front;

    printf("%d dequeued from queue.\n", temp->data);

    front = front->next;

  

    if (front == NULL) {

        // Queue became empty

        rear = NULL;

    }

  

    free(temp);

}

  

// Display queue

void displayQueue() {

    if (front == NULL) {

        printf("Queue is empty.\n");

        return;

    }

  

    struct Node* temp = front;

    printf("Queue elements (Front to Rear): ");

    while (temp != NULL) {

        printf("%d -> ", temp->data);

        temp = temp->next;

    }

    printf("NULL\n");

}

  

// Main menu

int main() {

    int choice, value;

  

    while (1) {

        printf("\n--- QUEUE OPERATIONS USING LINKED LIST ---\n");

        printf("1. Enqueue\n");

        printf("2. Dequeue\n");

        printf("3. Display Queue\n");

        printf("4. Exit\n");

        printf("Enter your choice: ");

        scanf("%d", &choice);

  

        switch (choice) {

        case 1:

            printf("Enter value to enqueue: ");

            scanf("%d", &value);

            enqueue(value);

            break;

        case 2:

            dequeue();

            break;

        case 3:

            displayQueue();

            break;

        case 4:

            printf("Exiting program.\n");

            exit(0);

        default:

            printf("Invalid choice. Please try again.\n");

        }

    }

    return 0;

}
```
```C
Output:

--- QUEUE OPERATIONS USING LINKED LIST ---

1. Enqueue

2. Dequeue

3. Display Queue

4. Exit

Enter your choice: <1>

Enter value to enqueue: <10>

10 enqueued to queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <1>

Enter value to enqueue: <20>

20 enqueued to queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <1>

Enter value to enqueue: <30>

30 enqueued to queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Queue elements (Front to Rear): 10 -> 20 -> 30 -> NULL

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

10 dequeued from queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Queue elements (Front to Rear): 20 -> 30 -> NULL

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

20 dequeued from queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

30 dequeued from queue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <2>

Queue Underflow. Nothing to dequeue.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <3>

Queue is empty.

  

--- QUEUE OPERATIONS USING LINKED LIST ---

Enter your choice: <4>

Exiting program.
```
  

Implementation of  circular queue using linked list:
```C
#include <stdio.h>

#include <stdlib.h>

  

// Node structure

struct Node {

    int data;

    struct Node* next;

};

  

struct Node* front = NULL;

struct Node* rear = NULL;

  

// Enqueue operation (insert at end)

void enqueue(int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->data = value;

  

    if (front == NULL) {

        // Queue is empty

        front = rear = newNode;

        newNode->next = front; // Point to itself

    } else {

        rear->next = newNode;

        rear = newNode;

        rear->next = front; // Maintain circular link

    }

    printf("%d enqueued.\n", value);

}

  

// Dequeue operation (delete from front)

void dequeue() {

    if (front == NULL) {

        printf("Queue Underflow. Nothing to dequeue.\n");

        return;

    }

  

    if (front == rear) {

        // Only one node

        printf("%d dequeued.\n", front->data);

        free(front);

        front = rear = NULL;

    } else {

        struct Node* temp = front;

        printf("%d dequeued.\n", temp->data);

        front = front->next;

        rear->next = front; // Maintain circular link

        free(temp);

    }

}

  

// Display queue

void displayQueue() {

    if (front == NULL) {

        printf("Queue is empty.\n");

        return;

    }

  

    struct Node* temp = front;

    printf("Circular Queue elements: ");

    do {

        printf("%d -> ", temp->data);

        temp = temp->next;

    } while (temp != front);

    printf("(front)\n");

}

  

// Main menu

int main() {

    int choice, value;

  

    while (1) {

        printf("\n--- CIRCULAR QUEUE USING LINKED LIST ---\n");

        printf("1. Enqueue\n");

        printf("2. Dequeue\n");

        printf("3. Display Queue\n");

        printf("4. Exit\n");

        printf("Enter your choice: ");

        scanf("%d", &choice);

  

        switch (choice) {

        case 1:

            printf("Enter value to enqueue: ");

            scanf("%d", &value);

            enqueue(value);

            break;

        case 2:

            dequeue();

            break;

        case 3:

            displayQueue();

            break;

        case 4:

            printf("Exiting program.\n");

            exit(0);

        default:

            printf("Invalid choice. Please try again.\n");

        }

    }

    return 0;

}
```
```C
Output:

--- CIRCULAR QUEUE USING LINKED LIST ---

1. Enqueue

2. Dequeue

3. Display Queue

4. Exit

Enter your choice: <1>

Enter value to enqueue: <10>

10 enqueued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <1>

Enter value to enqueue: <20>

20 enqueued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <1>

Enter value to enqueue: <30>

30 enqueued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <3>

Circular Queue elements: 10 -> 20 -> 30 -> (front)

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <2>

10 dequeued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <3>

Circular Queue elements: 20 -> 30 -> (front)

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <2>

20 dequeued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <2>

30 dequeued.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <2>

Queue Underflow. Nothing to dequeue.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <3>

Queue is empty.

  

--- CIRCULAR QUEUE USING LINKED LIST ---

Enter your choice: <4>

Exiting program.
```

Implementation of deque using linked list: 
```C
#include <stdio.h>

#include <stdlib.h>

  

// Node structure

struct Node {

    int data;

    struct Node* prev;

    struct Node* next;

};

  

struct Node* front = NULL;

struct Node* rear = NULL;

  

// Insert at front

void insertFront(int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->data = value;

    newNode->prev = NULL;

    newNode->next = front;

  

    if (front == NULL) {

        // Dequeue was empty

        front = rear = newNode;

    } else {

        front->prev = newNode;

        front = newNode;

    }

    printf("%d inserted at front.\n", value);

}

  

// Insert at rear

void insertRear(int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->data = value;

    newNode->next = NULL;

    newNode->prev = rear;

  

    if (rear == NULL) {

        // Dequeue was empty

        front = rear = newNode;

    } else {

        rear->next = newNode;

        rear = newNode;

    }

    printf("%d inserted at rear.\n", value);

}

  

// Delete from front

void deleteFront() {

    if (front == NULL) {

        printf("Dequeue Underflow. Nothing to delete.\n");

        return;

    }

  

    struct Node* temp = front;

    printf("%d deleted from front.\n", temp->data);

  

    if (front == rear) {

        // Only one node

        front = rear = NULL;

    } else {

        front = front->next;

        front->prev = NULL;

    }

    free(temp);

}

  

// Delete from rear

void deleteRear() {

    if (rear == NULL) {

        printf("Dequeue Underflow. Nothing to delete.\n");

        return;

    }

  

    struct Node* temp = rear;

    printf("%d deleted from rear.\n", temp->data);

  

    if (front == rear) {

        // Only one node

        front = rear = NULL;

    } else {

        rear = rear->prev;

        rear->next = NULL;

    }

    free(temp);

}

  

// Display the dequeue

void displayDequeue() {

    if (front == NULL) {

        printf("Dequeue is empty.\n");

        return;

    }

  

    struct Node* temp = front;

    printf("Dequeue elements (Front to Rear): ");

    while (temp != NULL) {

        printf("%d <-> ", temp->data);

        temp = temp->next;

    }

    printf("NULL\n");

}

  

// Main menu

int main() {

    int choice, value;

  

    while (1) {

        printf("\n--- DEQUEUE USING DOUBLY LINKED LIST ---\n");

        printf("1. Insert at front\n");

        printf("2. Insert at rear\n");

        printf("3. Delete from front\n");

        printf("4. Delete from rear\n");

        printf("5. Display Dequeue\n");

        printf("6. Exit\n");

        printf("Enter your choice: ");

        scanf("%d", &choice);

  

        switch (choice) {

        case 1:

            printf("Enter value to insert at front: ");

            scanf("%d", &value);

            insertFront(value);

            break;

        case 2:

            printf("Enter value to insert at rear: ");

            scanf("%d", &value);

            insertRear(value);

            break;

        case 3:

            deleteFront();

            break;

        case 4:

            deleteRear();

            break;

        case 5:

            displayDequeue();

            break;

        case 6:

            printf("Exiting program.\n");

            exit(0);

        default:

            printf("Invalid choice. Please try again.\n");

        }

    }

    return 0;

}
```

```C
Output: 

--- DEQUEUE USING DOUBLY LINKED LIST ---

1. Insert at front

2. Insert at rear

3. Delete from front

4. Delete from rear

5. Display Dequeue

6. Exit

Enter your choice: <1>

Enter value to insert at front: <10>

10 inserted at front.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <2>

Enter value to insert at rear: <20>

20 inserted at rear.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <1>

Enter value to insert at front: <5>

5 inserted at front.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <5>

Dequeue elements (Front to Rear): 5 <-> 10 <-> 20 <-> NULL

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <3>

5 deleted from front.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <5>

Dequeue elements (Front to Rear): 10 <-> 20 <-> NULL

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <4>

20 deleted from rear.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <5>

Dequeue elements (Front to Rear): 10 <-> NULL

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <4>

10 deleted from rear.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <5>

Dequeue is empty.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <3>

Dequeue Underflow. Nothing to delete.

  

--- DEQUEUE USING DOUBLY LINKED LIST ---

Enter your choice: <6>

Exiting program.
```
  

Implementation of 2-variable polynomial using linked list:
```C
#include <stdio.h>

#include <stdlib.h>

  

// Node structure for polynomial term

struct Node {

    int coeff;

    int powX;

    int powY;

    struct Node* next;

};

  

// Function to create a term node

struct Node* createNode(int coeff, int powX, int powY) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->coeff = coeff;

    newNode->powX = powX;

    newNode->powY = powY;

    newNode->next = NULL;

    return newNode;

}

  

// Insert term at the end

void insertTerm(struct Node** poly, int coeff, int powX, int powY) {

    struct Node* newNode = createNode(coeff, powX, powY);

    if (*poly == NULL) {

        *poly = newNode;

    } else {

        struct Node* temp = *poly;

        while (temp->next != NULL)

            temp = temp->next;

        temp->next = newNode;

    }

}

  

// Display polynomial

void displayPolynomial(struct Node* poly) {

    if (poly == NULL) {

        printf("0");

        return;

    }

    struct Node* temp = poly;

    while (temp != NULL) {

        printf("%+dx^%dy^%d ", temp->coeff, temp->powX, temp->powY);

        temp = temp->next;

    }

    printf("\n");

}

  

// Add two polynomials

struct Node* addPolynomials(struct Node* poly1, struct Node* poly2) {

    struct Node* result = NULL;

    struct Node* p1 = poly1;

    struct Node* p2 = poly2;

  

    while (p1 != NULL) {

        insertTerm(&result, p1->coeff, p1->powX, p1->powY);

        p1 = p1->next;

    }

  

    while (p2 != NULL) {

        // Try to find term with same powers

        struct Node* temp = result;

        int found = 0;

        while (temp != NULL) {

            if (temp->powX == p2->powX && temp->powY == p2->powY) {

                temp->coeff += p2->coeff;

                found = 1;

                break;

            }

            temp = temp->next;

        }

        if (!found) {

            insertTerm(&result, p2->coeff, p2->powX, p2->powY);

        }

        p2 = p2->next;

    }

    return result;

}

  

// Main

int main() {

    struct Node* poly1 = NULL;

    struct Node* poly2 = NULL;

    struct Node* sum = NULL;

  

    int n, coeff, powX, powY;

  

    printf("Enter number of terms in first polynomial: ");

    scanf("%d", &n);

    printf("Enter terms in format: coefficient powerX powerY\n");

    for (int i = 0; i < n; i++) {

        scanf("%d %d %d", &coeff, &powX, &powY);

        insertTerm(&poly1, coeff, powX, powY);

    }

  

    printf("Enter number of terms in second polynomial: ");

    scanf("%d", &n);

    printf("Enter terms in format: coefficient powerX powerY\n");

    for (int i = 0; i < n; i++) {

        scanf("%d %d %d", &coeff, &powX, &powY);

        insertTerm(&poly2, coeff, powX, powY);

    }

  

    printf("First Polynomial: ");

    displayPolynomial(poly1);

  

    printf("Second Polynomial: ");

    displayPolynomial(poly2);

  

    sum = addPolynomials(poly1, poly2);

  

    printf("Sum Polynomial: ");

    displayPolynomial(sum);

  

    return 0;

}
```
```C
Output:

Enter number of terms in first polynomial: 3

Enter terms in format: coefficient powerX powerY

3 2 1

5 1 0

-2 0 2

Enter number of terms in second polynomial: 3

Enter terms in format: coefficient powerX powerY

4 2 1

6 0 2

1 3 0

First Polynomial: +3x^2y^1 +5x^1y^0 +-2x^0y^2 

Second Polynomial: +4x^2y^1 +6x^0y^2 +1x^3y^0 

Sum Polynomial: +7x^2y^1 +5x^1y^0 +4x^0y^2 +1x^3y^0
```


Implementation of sparse matrix using linked list:
```C
#include <stdio.h>

#include <stdlib.h>

  

// Node structure

struct Node {

    int row;

    int col;

    int value;

    struct Node* next;

};

  

// Create a new node

struct Node* createNode(int row, int col, int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    newNode->row = row;

    newNode->col = col;

    newNode->value = value;

    newNode->next = NULL;

    return newNode;

}

  

// Insert node at end

void insertNode(struct Node** head, int row, int col, int value) {

    struct Node* newNode = createNode(row, col, value);

    if (*head == NULL) {

        *head = newNode;

    } else {

        struct Node* temp = *head;

        while (temp->next != NULL)

            temp = temp->next;

        temp->next = newNode;

    }

}

  

// Display sparse matrix

void displaySparse(struct Node* head) {

    if (head == NULL) {

        printf("Empty matrix.\n");

        return;

    }

    printf("Row Col Value\n");

    struct Node* temp = head;

    while (temp != NULL) {

        printf("%d   %d   %d\n", temp->row, temp->col, temp->value);

        temp = temp->next;

    }

}

  

// Add two sparse matrices

struct Node* addSparse(struct Node* m1, struct Node* m2) {

    struct Node* result = NULL;

    struct Node* p1 = m1;

    struct Node* p2 = m2;

  

    while (p1 != NULL) {

        insertNode(&result, p1->row, p1->col, p1->value);

        p1 = p1->next;

    }

  

    while (p2 != NULL) {

        struct Node* temp = result;

        int found = 0;

        while (temp != NULL) {

            if (temp->row == p2->row && temp->col == p2->col) {

                temp->value += p2->value;

                found = 1;

                break;

            }

            temp = temp->next;

        }

        if (!found) {

            insertNode(&result, p2->row, p2->col, p2->value);

        }

        p2 = p2->next;

    }

    return result;

}

  

// Transpose sparse matrix

struct Node* transposeSparse(struct Node* matrix) {

    struct Node* result = NULL;

    struct Node* temp = matrix;

    while (temp != NULL) {

        insertNode(&result, temp->col, temp->row, temp->value);

        temp = temp->next;

    }

    return result;

}

  

// Main

int main() {

    struct Node* matrix1 = NULL;

    struct Node* matrix2 = NULL;

    struct Node* sum = NULL;

    struct Node* transposed = NULL;

  

    int n, row, col, value;

  

    printf("Enter number of non-zero elements in first matrix: ");

    scanf("%d", &n);

    printf("Enter elements in format: row column value\n");

    for (int i = 0; i < n; i++) {

        scanf("%d %d %d", &row, &col, &value);

        insertNode(&matrix1, row, col, value);

    }

  

    printf("Enter number of non-zero elements in second matrix: ");

    scanf("%d", &n);

    printf("Enter elements in format: row column value\n");

    for (int i = 0; i < n; i++) {

        scanf("%d %d %d", &row, &col, &value);

        insertNode(&matrix2, row, col, value);

    }

  

    printf("\nFirst Sparse Matrix:\n");

    displaySparse(matrix1);

  

    printf("\nSecond Sparse Matrix:\n");

    displaySparse(matrix2);

  

    sum = addSparse(matrix1, matrix2);

    printf("\nSum Sparse Matrix:\n");

    displaySparse(sum);

  

    transposed = transposeSparse(matrix1);

    printf("\nTranspose of First Sparse Matrix:\n");

    displaySparse(transposed);

  

    return 0;

}
```
```C
Output:

Enter number of non-zero elements in first matrix: 3

Enter elements in format: row column value

0 0 5

0 2 8

1 1 3

Enter number of non-zero elements in second matrix: 2

Enter elements in format: row column value

0 2 7

1 0 4

  

First Sparse Matrix:

Row Col Value

0   0   5

0   2   8

1   1   3

  

Second Sparse Matrix:

Row Col Value

0   2   7

1   0   4

  

Sum Sparse Matrix:

Row Col Value

0   0   5         (from first)

0   2   15        (8+7)

1   1   3         (from first)

1   0   4         (from second)

  

Transpose of First Sparse Matrix:

Row Col Value

0   0   5

2   0   8

1   1   3
```
