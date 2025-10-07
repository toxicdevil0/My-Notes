Experiment 1: Write a simple C program on a 32 bit compiler to understand
the concept of array storage, size of a word.The program shall be written
illustrating the concept of row major and column major storage. Find the
address of element and verify it with the theoretical value. Programe may be
written for arrays up to 4,dimensions.
Row Major Method:
```c
#include <stdio.h>
int main() {
	int rows, cols, baseAddress, elementSize, row, col;
	printf("Enter the number of rows: ");
	scanf("%d", &rows);
	printf("Enter the number of columns: ");
	scanf("%d", &cols);
	printf("Enter the base address of the array: ");
	scanf("%d", &baseAddress);
	printf("Enter the size of each element (in bytes): ");
	scanf("%d", &elementSize);
	printf("Enter the row index of the element (0-based): ");
	scanf("%d", &row);
	printf("Enter the column index of the element (0-based): ");
	scanf("%d", &col);
	// Row major order formula: base + ((row * number of columns) + col) * element size
	int address = baseAddress + ((row * cols) + col) * elementSize;
	printf("The address of element [%d][%d] is: %d\n", row, col, address);
	return 0;
}
```
Output:
```
Enter the number of rows: <5>
Enter the number of columns: <8>
Enter the base address of the array: <5000>
Enter the size of each element (in bytes): <2>
Enter the row index of the element (0-based): <3>
Enter the column index of the element (0-based): <6>
The address of element [3][6] is: 5000 + (3*8 + 6)*2 = 5000 + (24+6)*2 = 5000 + 60 = 5060
```
Column Major Method:
```c
#include <stdio.h>
int main() {
	int rows, cols, base_address, element_size, row_index, col_index;
	int address;
	// Get array dimensions and other parameters from the user.
	printf("Enter the number of rows: ");
	scanf("%d", &rows);
	printf("Enter the number of columns: ");
	scanf("%d", &cols);
	printf("Enter the base address: ");
	scanf("%d", &base_address);
	printf("Enter the size of each element (in bytes): ");
	scanf("%d", &element_size);
	printf("Enter the row index of the element: ");
	scanf("%d", &row_index);
	printf("Enter the column index of the element: ");
	scanf("%d", &col_index);
	// Calculate the address using the column-major formula.
	address = base_address + element_size * ((row_index) + rows * (col_index));
	// Print the calculated address.
	printf("The address of element [%d][%d] is: %d\n", row_index, col_index,
	address);
	return 0;
}
```
Output:
```
Enter the number of rows: <3>
Enter the number of columns: <4>
Enter the base address: <1000>
Enter the size of each element (in bytes): <4>
Enter the row index of the element: <2>
Enter the column index of the element: <1>
The address of element [2][1] is: 1020
```
#### Experiment 2: 
**Simulate a stack, queue, circular queue and dequeue using a**
**one dimensional array as storage element. The program should implement**
**the basic addition, deletion and traversal operations.**
Implementation of Stack:
```c
#include <stdio.h>
#include <stdlib.h>
#define MAX 5 // Size of the stack
int stack[MAX]; // Stack array
int top = -1; // Stack pointer
// Function to push an element into the stack
void push(int val){
	if (top == MAX - 1){
	printf("Stack Overflow! Cannot push %d\n", val);
	}
	else {
	top++;
	stack[top] = val;
	printf("%d pushed onto the stack.\n", val);
	}
}
// Function to pop an element from the stack
void pop() {
if (top == -1) {
	printf("Stack Underflow! Nothing to pop.\n");
	} else {
	printf("%d popped from the stack.\n", stack[top]);
	top--;
	}
}
// Function to display the elements of the stack
void display() {
	if (top == -1) {
	printf("Stack is empty.\n");
	} else {
	printf("Stack elements:\n");
	for (int i = top; i >= 0; i--) {
		printf("%d\n", stack[i]);
		}
	}
}
// Main function with menu
int main() {
	int choice, val;
	while (1) {
		printf("\n--- STACK OPERATIONS ---\n");
		printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
		printf("Enter your choice: ");
		scanf("%d", &choice);
		switch (choice) {
		case 1:
			printf("Enter value to push: ");
			scanf("%d", &val);
			push(val);
		break;
		
		case 2:
			pop();
		break;
		
		case 3:
			display();
		break;
		
		case 4:
			printf("Exiting...\n");
			exit(0);
		default:
			printf("Invalid choice. Please try again.\n");
		}
	}
	return 0;
}
```
Output:
```
--- STACK OPERATIONS ---
1. Push
2. Pop
3. Display
4. Exit
Enter your choice: 1
Enter value to push: 10
10 pushed onto the stack.
--- STACK OPERATIONS ---
5. Push
6. Pop
7. Display
8. Exit
Enter your choice: 1
Enter value to push: 20
20 pushed onto the stack.
--- STACK OPERATIONS ---
9. Push
10. Pop
11. Display
12. Exit
Enter your choice: 1
Enter value to push: 30
30 pushed onto the stack.
--- STACK OPERATIONS ---
13. Push
14. Pop
15. Display
16. Exit
Enter your choice: 3
Stack elements:
30
20
10
--- STACK OPERATIONS ---
17. Push
18. Pop
19. Display
20. Exit
Enter your choice: 2
30 popped from the stack.
--- STACK OPERATIONS ---
21. Push
22. Pop
23. Display
24. Exit
Enter your choice: 2
20 popped from the stack.
--- STACK OPERATIONS ---
25. Push
26. Pop
27. Display
28. Exit
Enter your choice: 2
10 popped from the stack.
--- STACK OPERATIONS ---
29. Push
30. Pop
31. Display
32. Exit
Enter your choice: 2
Stack Underflow! Nothing to pop.
--- STACK OPERATIONS ---
33. Push
34. Pop
35. Display
36. Exit
Enter your choice: 3
Stack is empty.
--- STACK OPERATIONS ---
37. Push
38. Pop
39. Display
40. Exit
Enter your choice: 1
Enter value to push: 40
40 pushed onto the stack.
--- STACK OPERATIONS ---
41. Push
42. Pop
43. Display
44. Exit
Enter your choice: 1
Enter value to push: 50
50 pushed onto the stack.
--- STACK OPERATIONS ---
45. Push
46. Pop
47. Display
48. Exit
Enter your choice: 1
Enter value to push: 60
60 pushed onto the stack.
--- STACK OPERATIONS ---
49. Push
50. Pop
51. Display
52. Exit
Enter your choice: 1
Enter value to push: 70
70 pushed onto the stack.
--- STACK OPERATIONS ---
53. Push
54. Pop
55. Display
56. Exit
Enter your choice: 1
Enter value to push: 80
80 pushed onto the stack.
--- STACK OPERATIONS ---
57. Push
58. Pop
59. Display
60. Exit
Enter your choice: 1
Enter value to push: 90
Stack Overflow! Cannot push 90
--- STACK OPERATIONS ---
61. Push
62. Pop
63. Display
64. Exit
Enter your choice: 3
Stack elements:
80
70
60
50
40
--- STACK OPERATIONS ---
65. Push
66. Pop
67. Display
68. Exit
Enter your choice: 4
Exiting...
```
Implementation of Queue:
```c
#include <stdio.h>
#include <stdlib.h>
#define MAX 5 // Maximum size of the queue
int queue[MAX];
int front = -1; // Points to the front element
int rear = -1; // Points to the last element
// Function to add an element (enqueue)
void enqueue(int value) {
	if (rear == MAX - 1) {
		printf("Queue Overflow! Cannot enqueue %d.\n", value);
	} else {
	if (front == -1) {
		front = 0; // Initialize front on first insertion
	}
	rear++;
	queue[rear] = value;
	printf("%d enqueued into the queue.\n", value);
	}
}
// Function to delete an element (dequeue)
void dequeue() {
	if (front == -1 || front > rear) {
		printf("Queue Underflow! Nothing to dequeue.\n");
	} else {
		printf("%d dequeued from the queue.\n", queue[front]);
		front++;
		// Reset pointers if queue becomes empty
		if (front > rear) {
			front = rear = -1;
		}
	}
}
// Function to display the queue (traversal)
void display() {
	if (front == -1) {
		printf("Queue is empty.\n");
	} else {
		printf("Queue elements:\n");
		for (int i = front; i <= rear; i++) {
			printf("%d ", queue[i]);
		}
		printf("\n");
	}
}
// Main function
int main() {
	int choice, value;
	while (1) {
		printf("\n--- QUEUE OPERATIONS ---\n");
		printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
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
			display();
		break;
		
		case 4:
			printf("Exiting program...\n");
			exit(0);
			
		default:
			printf("Invalid choice. Please try again.\n");
		}
	}
	return 0;
}
```
Output:
```
--- QUEUE OPERATIONS ---
1. Enqueue
2. Dequeue
3. Display
4. Exit
Enter your choice: 1
Enter value to enqueue: 10
10 enqueued into the queue.
--- QUEUE OPERATIONS ---
5. Enqueue
6. Dequeue
7. Display
8. Exit
Enter your choice: 1
Enter value to enqueue: 20
20 enqueued into the queue.
--- QUEUE OPERATIONS ---
9. Enqueue
10. Dequeue
11. Display
12. Exit
Enter your choice: 1
Enter value to enqueue: 30
30 enqueued into the queue.
--- QUEUE OPERATIONS ---
13. Enqueue
14. Dequeue
15. Display
16. Exit
Enter your choice: 3
Queue elements:
10 20 30
--- QUEUE OPERATIONS ---
17. Enqueue
18. Dequeue
19. Display
20. Exit
Enter your choice: 2
10 dequeued from the queue.
--- QUEUE OPERATIONS ---
21. Enqueue
22. Dequeue
23. Display
24. Exit
Enter your choice: 2
20 dequeued from the queue.
--- QUEUE OPERATIONS ---
25. Enqueue
26. Dequeue
27. Display
28. Exit
Enter your choice: 3
Queue elements:
30
--- QUEUE OPERATIONS ---
29. Enqueue
30. Dequeue
31. Display
32. Exit
Enter your choice: 1
Enter value to enqueue: 40
40 enqueued into the queue.
--- QUEUE OPERATIONS ---
33. Enqueue
34. Dequeue
35. Display
36. Exit
Enter your choice: 1
Enter value to enqueue: 50
50 enqueued into the queue.
--- QUEUE OPERATIONS ---
37. Enqueue
38. Dequeue
39. Display
40. Exit
Enter your choice: 1
Enter value to enqueue: 60
60 enqueued into the queue.
--- QUEUE OPERATIONS ---
41. Enqueue
42. Dequeue
43. Display
44. Exit
Enter your choice: 1
Enter value to enqueue: 70
Queue Overflow! Cannot enqueue 70.
--- QUEUE OPERATIONS ---
45. Enqueue
46. Dequeue
47. Display
48. Exit
Enter your choice: 3
Queue elements:
30 40 50 60
--- QUEUE OPERATIONS ---
49. Enqueue
50. Dequeue
51. Display
52. Exit
Enter your choice: 2
30 dequeued from the queue.
--- QUEUE OPERATIONS ---
53. Enqueue
54. Dequeue
55. Display
56. Exit
Enter your choice: 2
40 dequeued from the queue.
--- QUEUE OPERATIONS ---
57. Enqueue
58. Dequeue
59. Display
60. Exit
Enter your choice: 2
50 dequeued from the queue.
--- QUEUE OPERATIONS ---
61. Enqueue
62. Dequeue
63. Display
64. Exit
Enter your choice: 2
60 dequeued from the queue.
--- QUEUE OPERATIONS ---
65. Enqueue
66. Dequeue
67. Display
68. Exit
Enter your choice: 2
Queue Underflow! Nothing to dequeue.
--- QUEUE OPERATIONS ---
69. Enqueue
70. Dequeue
71. Display
72. Exit
Enter your choice: 3
Queue is empty.
--- QUEUE OPERATIONS ---
73. Enqueue
74. Dequeue
75. Display
76. Exit
Enter your choice: 4
Exiting program...
```
Implementation of circular queue:
```c
#include <stdio.h>
#include <stdlib.h>
#define MAX 5 // Maximum size of the circular queue
int cqueue[MAX];
int front = -1;
int rear = -1;
// Function to insert an element (enqueue)
void enqueue(int value) {
	if ((front == 0 && rear == MAX - 1) || (rear + 1) % MAX == front) {
		printf("Circular Queue Overflow! Cannot enqueue %d.\n", value);
	} else {
	if (front == -1) {
	// First element
		front = 0;
		rear = 0;
	} else {
		rear = (rear + 1) % MAX;
	}
		cqueue[rear] = value;
		printf("%d enqueued into the circular queue.\n", value);
	}
}
// Function to delete an element (dequeue)
void dequeue() {
	if (front == -1) {
		printf("Circular Queue Underflow! Nothing to dequeue.\n");
	} else {
		printf("%d dequeued from the circular queue.\n", cqueue[front]);
		if (front == rear) {
			// Queue becomes empty
			front = -1;
			rear = -1;
		} else {
			front = (front + 1) % MAX;
		}
	}
}
// Function to display the circular queue
void display() {
	if (front == -1) {
		printf("Circular Queue is empty.\n");
	} else {
		printf("Circular Queue elements:\n");
		int i = front;
		while (1) {
			printf("%d ", cqueue[i]);
			if (i == rear) {
				break;
			}
			i = (i + 1) % MAX;
		}
		printf("\n");
	}
}
// Main function
int main() {
	int choice, value;
	while (1) {
		printf("\n--- CIRCULAR QUEUE OPERATIONS ---\n");
		printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
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
			display();
		break;
		
		case 4:
			printf("Exiting program...\n");
			exit(0);
			
		default:
			printf("Invalid choice. Please try again.\n");
		}
	}
	return 0;
}
```
Output:
```
--- CIRCULAR QUEUE OPERATIONS ---
1. Enqueue
2. Dequeue
3. Display
4. Exit
Enter your choice: 1
Enter value to enqueue: 10
10 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
5. Enqueue
6. Dequeue
7. Display
8. Exit
Enter your choice: 1
Enter value to enqueue: 20
20 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
9. Enqueue
10. Dequeue
11. Display
12. Exit
Enter your choice: 1
Enter value to enqueue: 30
30 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
13. Enqueue
14. Dequeue
15. Display
16. Exit
Enter your choice: 3
Circular Queue elements:
10 20 30
--- CIRCULAR QUEUE OPERATIONS ---
17. Enqueue
18. Dequeue
19. Display
20. Exit
Enter your choice: 2
10 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
21. Enqueue
22. Dequeue
23. Display
24. Exit
Enter your choice: 2
20 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
25. Enqueue
26. Dequeue
27. Display
28. Exit
Enter your choice: 1
Enter value to enqueue: 40
40 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
29. Enqueue
30. Dequeue
31. Display
32. Exit
Enter your choice: 1
Enter value to enqueue: 50
50 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
33. Enqueue
34. Dequeue
35. Display
36. Exit
Enter your choice: 1
Enter value to enqueue: 60
60 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
37. Enqueue
38. Dequeue
39. Display
40. Exit
Enter your choice: 3
Circular Queue elements:
30 40 50 60
--- CIRCULAR QUEUE OPERATIONS ---
41. Enqueue
42. Dequeue
43. Display
44. Exit
Enter your choice: 1
Enter value to enqueue: 70
70 enqueued into the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
45. Enqueue
46. Dequeue
47. Display
48. Exit
Enter your choice: 1
Enter value to enqueue: 80
Circular Queue Overflow! Cannot enqueue 80.
--- CIRCULAR QUEUE OPERATIONS ---
49. Enqueue
50. Dequeue
51. Display
52. Exit
Enter your choice: 3
Circular Queue elements:
30 40 50 60 70
--- CIRCULAR QUEUE OPERATIONS ---
53. Enqueue
54. Dequeue
55. Display
56. Exit
Enter your choice: 2
30 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
57. Enqueue
58. Dequeue
59. Display
60. Exit
Enter your choice: 2
40 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
61. Enqueue
62. Dequeue
63. Display
64. Exit
Enter your choice: 2
50 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
65. Enqueue
66. Dequeue
67. Display
68. Exit
Enter your choice: 2
60 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
69. Enqueue
70. Dequeue
71. Display
72. Exit
Enter your choice: 2
70 dequeued from the circular queue.
--- CIRCULAR QUEUE OPERATIONS ---
73. Enqueue
74. Dequeue
75. Display
76. Exit
Enter your choice: 2
Circular Queue Underflow! Nothing to dequeue.
--- CIRCULAR QUEUE OPERATIONS ---
77. Enqueue
78. Dequeue
79. Display
80. Exit
Enter your choice: 3
Circular Queue is empty.
--- CIRCULAR QUEUE OPERATIONS ---
81. Enqueue
82. Dequeue
83. Display
84. Exit
Enter your choice: 4
Exiting program...
```


Implementation of deque:
```c
#include <stdio.h>
#include <stdlib.h>
#define MAX 5 // Maximum size of the dequeue
int deque[MAX];
int front = -1;
int rear = -1;
// Insert at front
void insertFront(int value) {
	if ((front == 0 && rear == MAX - 1) || (front == rear + 1)) {
		printf("Dequeue Overflow! Cannot insert %d at front.\n", value);
	} else {
		if (front == -1) { // Empty deque
			front = rear = 0;
		} else if (front == 0) {
			front = MAX - 1;
		} else {
			front--;
		}
		deque[front] = value;
		printf("%d inserted at front.\n", value);
	}
}
// Insert at rear
void insertRear(int value) {
	if ((front == 0 && rear == MAX - 1) || (front == rear + 1)) {
		printf("Dequeue Overflow! Cannot insert %d at rear.\n", value);
	} else {
		if (front == -1) { // Empty deque
			front = rear = 0;
		} else if (rear == MAX - 1) {
			rear = 0;
		} else {
			rear++;
		}
		deque[rear] = value;
		printf("%d inserted at rear.\n", value);
	}
}
// Delete from front
void deleteFront() {
	if (front == -1) {
		printf("Dequeue Underflow! Nothing to delete at front.\n");
	} else {
		printf("%d deleted from front.\n", deque[front]);
		if (front == rear) {
			front = rear = -1; // Queue becomes empty
		} else if (front == MAX - 1) {
			front = 0;
		} else {
			front++;
		}
	}
}
// Delete from rear
void deleteRear() {
	if (front == -1) {
		printf("Dequeue Underflow! Nothing to delete at rear.\n");
	} else {
	printf("%d deleted from rear.\n", deque[rear]);
		if (front == rear) {
			front = rear = -1; // Queue becomes empty
		} else if (rear == 0) {
			rear = MAX - 1;
		} else {
			rear--;
		}
	}
}
// Display all elements
void display() {
	if (front == -1) {
		printf("Dequeue is empty.\n");
		} else {
			printf("Dequeue elements:\n");
			int i = front;
			while (1) {
				printf("%d ", deque[i]);
				if (i == rear) {
				break;
			}
			i = (i + 1) % MAX;
		}
		printf("\n");
	}
}
// Main menu
int main() {
	int choice, value;
	while (1) {
		printf("\n--- DEQUEUE OPERATIONS ---\n");
		printf("1. Insert Front\n");
		printf("2. Insert Rear\n");
		printf("3. Delete Front\n");
		printf("4. Delete Rear\n");
		printf("5. Display\n");
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
				display();
			break;
			
			case 6:
				printf("Exiting program...\n");
				exit(0);
				
			default:
				printf("Invalid choice. Please try again.\n");
			}
		}
	return 0;
}
```
Output:
```
--- DEQUEUE OPERATIONS ---
1. Insert Front
2. Insert Rear
3. Delete Front
4. Delete Rear
5. Display
6. Exit
Enter your choice: 1
Enter value to insert at front: 10
10 inserted at front.
--- DEQUEUE OPERATIONS ---
7. Insert Front
8. Insert Rear
9. Delete Front
10. Delete Rear
11. Display
12. Exit
Enter your choice: 2
Enter value to insert at rear: 20
20 inserted at rear.
--- DEQUEUE OPERATIONS ---
13. Insert Front
14. Insert Rear
15. Delete Front
16. Delete Rear
17. Display
18. Exit
Enter your choice: 1
Enter value to insert at front: 5
5 inserted at front.
--- DEQUEUE OPERATIONS ---
19. Insert Front
20. Insert Rear
21. Delete Front
22. Delete Rear
23. Display
24. Exit
Enter your choice: 2
Enter value to insert at rear: 25
25 inserted at rear.
--- DEQUEUE OPERATIONS ---
25. Insert Front
26. Insert Rear
27. Delete Front
28. Delete Rear
29. Display
30. Exit
Enter your choice: 2
Enter value to insert at rear: 30
30 inserted at rear.
--- DEQUEUE OPERATIONS ---
31. Insert Front
32. Insert Rear
33. Delete Front
34. Delete Rear
35. Display
36. Exit
Enter your choice: 2
Enter value to insert at rear: 35
Dequeue Overflow! Cannot insert 35 at rear.
--- DEQUEUE OPERATIONS ---
37. Insert Front
38. Insert Rear
39. Delete Front
40. Delete Rear
41. Display
42. Exit
Enter your choice: 5
Dequeue elements:
5 10 20 25 30
--- DEQUEUE OPERATIONS ---
43. Insert Front
44. Insert Rear
45. Delete Front
46. Delete Rear
47. Display
48. Exit
Enter your choice: 3
5 deleted from front.
--- DEQUEUE OPERATIONS ---
49. Insert Front
50. Insert Rear
51. Delete Front
52. Delete Rear
53. Display
54. Exit
Enter your choice: 4
30 deleted from rear.
--- DEQUEUE OPERATIONS ---
55. Insert Front
56. Insert Rear
57. Delete Front
58. Delete Rear
59. Display
60. Exit
Enter your choice: 5
Dequeue elements:
10 20 25
--- DEQUEUE OPERATIONS ---
61. Insert Front
62. Insert Rear
63. Delete Front
64. Delete Rear
65. Display
66. Exit
Enter your choice: 1
Enter value to insert at front: 1
1 inserted at front.
--- DEQUEUE OPERATIONS ---
67. Insert Front
68. Insert Rear
69. Delete Front
70. Delete Rear
71. Display
72. Exit
Enter your choice: 5
Dequeue elements:
1 10 20 25
--- DEQUEUE OPERATIONS ---
73. Insert Front
74. Insert Rear
75. Delete Front
76. Delete Rear
77. Display
78. Exit
Enter your choice: 3
1 deleted from front.
--- DEQUEUE OPERATIONS ---
79. Insert Front
80. Insert Rear
81. Delete Front
82. Delete Rear
83. Display
84. Exit
Enter your choice: 3
10 deleted from front.
--- DEQUEUE OPERATIONS ---
85. Insert Front
86. Insert Rear
87. Delete Front
88. Delete Rear
89. Display
90. Exit
Enter your choice: 3
20 deleted from front.
--- DEQUEUE OPERATIONS ---
91. Insert Front
92. Insert Rear
93. Delete Front
94. Delete Rear
95. Display
96. Exit
Enter your choice: 3
25 deleted from front.
--- DEQUEUE OPERATIONS ---
97. Insert Front
98. Insert Rear
99. Delete Front
100. Delete Rear
101. Display
102. Exit
Enter your choice: 3
Dequeue Underflow! Nothing to delete at front.
--- DEQUEUE OPERATIONS ---
103. Insert Front
104. Insert Rear
105. Delete Front
106. Delete Rear
107. Display
108. Exit
Enter your choice: 5
Dequeue is empty.
--- DEQUEUE OPERATIONS ---
109. Insert Front
110. Insert Rear
111. Delete Front
112. Delete Rear
113. Display
114. Exit
Enter your choice: 6
Exiting program...
```