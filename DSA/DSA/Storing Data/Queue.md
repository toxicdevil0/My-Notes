Queues are also made using Arrays, they are based on the **FIFO Concept** (which stands for First In First Out). Where Stack is like books on top of each other, Queue is like a line at a cafeteria, where the first one to come to will be the first one to go out with the stuff (except in the priority queue where the element goes out based on their priority) 

Queue has two components- **Front and Rear**

![[Drawing 2025-08-21 01.17.29.excalidraw | 580]]

I don't wanna waste my time by writing algorithms for all the different methods in queue as it's quite same to that of Stack accept of there being two pointers except one.

here's the full code-
## Code-
```java
package Queue;  
  
public class Queue {  
    private int[] queue;  
    private int front;  
    private int rear;  
    private int capacity;  
    
    public Queue(int capacity) {  
        this.capacity = capacity;  
        this.queue = new int[capacity];  
        this.front = -1;  
        this.rear = -1;  
    }  
    
    public void enqueue(int x) {  
        if (isFull()) {  
            System.out.println("Queue overflow! Cannot enqueue " + x);  
            return;  
        }        if (isEmpty()) {  
            front = 0; // first element being inserted  
        }  
        queue[++rear] = x;  
    }  
    
    public void dequeue() {  
        if (isEmpty()) {  
            System.out.println("Queue underflow! Cannot dequeue from empty queue");  
        } else {  
            System.out.println("Element to be dequeued : " + queue[front]);  
            if (front == rear) {  
                // Last element removed, reset the queue  
                front = rear = -1;  
            } else {  
                front++;  
            }       
        }    
    }
      
    public int peek() {  
        if (isEmpty()) {  
            System.out.println("Queue is empty");  
            return -1;  
        } else {  
            return queue[front];  
        }    
    }
      
    public int size() {  
        if (isEmpty()) {  
            return 0;  
        }        return rear - front + 1;  
    }  
    
    public void display() {  
        if (isEmpty()) {  
            System.out.println("Queue is empty");  
        } else {  
            for (int i = front; i <= rear; i++) {  
                System.out.println(queue[i]);  
            }        
        }    
    }
      
    public boolean isFull() {  
        return rear == capacity - 1;  
    } 
     
    public boolean isEmpty() {  
        return front == -1;  
    }
    
}
```
---
[[Data Structures and Algorithms]]
