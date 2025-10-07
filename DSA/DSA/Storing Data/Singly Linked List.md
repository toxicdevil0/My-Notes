In linked list every box in which elements are added into are called nodes.
These Nodes are to be declared to have two things, the element itself and the address to next node.
To declare this Node we make a class named as Node
 ```java
 private class Node{  
	
    private int val;  
    private Node next;  
	  
    public Node (int val) {  
		  
        this.val = val;  
    }    
    public Node(int val, Node next){  
        this.val = val;  
        this.next = next;  
		  
	}
}
```

## Implementation in Java is as follows

```java
// Custom implementation of a singly linked list  
// Maintains references to both head and tail for 
public class NewLL {  
	  
    private Node head;  // Points to the first node in the list  
    private Node tail;  // Points to the last node in the list  
    private int size;   // Keeps track of the number of elements  
      
	// Constructor: Initializes an empty linked list  
    public NewLL(){  
        this.size = 0;  
    }  
    
    // Inner class representing a single node in the linked list  
    private class Node{
		  
        private int val;    // Data stored in the node  
        private Node next;  // Reference to the next node  
		  
        // Constructor: Creates a node with given value        
        // @param val - the value to store in this node        
        public Node (int val) {  
            this.val = val;  
        }        
        
        // Constructor: Creates a node with value and next reference  
        // @param val - the value to store in this node        
        // @param next - reference to the next node        
        public Node(int val, Node next){  
            this.val = val;  
            this.next = next;  
	    }    
	}
}  
```

### 1. Algo for inserting at the head-
1. define method insertAtFirst
	1. make a new obj node in class Node
	2. point the new node to current head and update head to new node
	3. if list is empty or (tail == null) then update so that tail = head
	4. increment size by 1
2. exit
#### Code for inserting at the head-
```java
// Inserts a new node at the beginning of the list  
// Time Complexity: O(1)    
// @param val - the value to insert    
public void insertAtFirst(int val){  
	Node node = new Node(val);  // Create new node  
	  
	node.next = head;  // Point new node to current head  
	head = node;       // Update head to point to new node  
	  
	// If list was empty, tail should also point to the new node        
	if(tail == null){  
		tail = head;  
	}        
	size++;  // Increment size counter  
}  
```

### 2. Algo for inserting at the tail end-
1. define method insertAtLast
	1. create a new obj node in class Node
	2. if list is empty or (head == null) use insertaAtFirst and exit
	3. point the tail to new the node or tail.next = node
	4. update tail to the new node or tail = node
	5. increment size by 1
2. exit
#### Code for inserting at the tail-
```java
// Inserts a new node at the end of the list  
// Time Complexity: O(1) - thanks to tail pointer    
// @param val - the value to insert    
public void insertAtLast(int val){  
	Node node = new Node(val);  // Create new node  
	  
	// If list is empty, use insertAtFirst method        
	if(tail == null){  
		insertAtFirst(val);  
		return;  
	}        
	// Link current tail to new node and update tail pointer  
	tail.next = node;  
	tail = node;  
	size++;  // Increment size counter  
}  
```

### 3. Algo to display the elements of the list-
1. define method traverse
	1. create new Node named temp and point it to head
	2. if list is empty or (tail == null) then print "List is empty" and exit
	3. repeat substep 1. untill temp is not null
		1. print the value inside temp and move to next node or temp = temp.next
2. exit
#### Code to display the elements of the list-
```java
// Traverses and displays all elements in the list  
// Time Complexity: O(n) where n is the number of elements    
public void traverse(){  
	Node temp = head;  // Start from the head  
	  
	// Check if list is empty        
	if(head == null){  
		System.out.println("List is empty");  
		return;  
	}        
	// Traverse through each node until we reach the end  
	while (temp != null){  
		System.out.print(temp.val + " -> ");  
		temp = temp.next;  // Move to next node  
	}  
	System.out.println("END");  // Indicate end of list  
}  
```

### 4. Algo to delete at the head-
1. define method deleteAtFirst
	1. if list is empty or (head == null) print list is empty and exit
	2. print element to be deleted which is the value in current head
	3. and point the head to the next node or head = head.next
	4. if list has only a single node or (head == tail) then put tail = null 
	5. decrement size by 1
2. exit
#### Code to delete at the head-
```java
// Deletes the first node from the list  
// Time Complexity: O(1)    
public void deleteAtFirst(){  
	// Check if list is empty  
	if (head == null){  
		System.out.println("List is empty");  
		return;  
	}        
	System.out.println("Element to be deleted: "+ head.val);  
	head = head.next;  // Move head to the next node  
	
	// If list has only a single node, update tail  
	if (head == null) {  
		tail = null;  
	}        
	size--;  // Decrement size counter  
}  
```

### 5. Algo to delete at the tail end-
1. define method deleteAtLast
	1. if list is empty or (head == null) then print list is empty and exit
	2. if list has only a single node or (head == tail) then 
	   print the element to be deleted which is the value inside the current head or head.val *(it can be tail as well cuz head and tail are equal)* and put both head and tail equal to null
	   decrement size by 1 and exit
	3. print element to be deleted which is the value inside the current tail or tail.val
	4. create Node temp and point to head
	5. repeat substep 1 for i = 0 to size - 2 **To get to the second last element**
		1. traverse temp to next node till second last node or temp = temp.next
	6. after temp gets to second last index in the list point tail to temp or tail = temp
	7. point temp.next to null
	8. decrement size by 1
2. exit
#### Code to delete at the tail end-
```java
// Deletes the last node from the list  
// Time Complexity: O(n) - needs to traverse to second-to-last node 
   
public void deleteAtLast(){  
	  
	// Check if list is empty  
	if (head == null){  
		System.out.println("List is empty");  
		return;  
	}  
	// Handle single node case  
	if (head == tail){  
		System.out.println("Element to be deleted: "+ head.val);  
		head = null;  
		tail = null;  
		size--;  
		return;  
	}  
	System.out.println("Element to be deleted: "+ tail.val);  
	  
	// Traverse to the second-to-last node  
	Node temp = head;  
	for (int i = 0; i < size - 2; i++) {  
		temp = temp.next;  
	}  
	// Update tail to second-to-last node and remove reference to deleted node  
	tail = temp;  
	tail.next = null;  
	size--;  // Decrement size counter  
}  
```

### 6. Algo to delete at certain index-
1. define method deleteAtIndex
	1. if list is empty or (head == null) then print list is empty and exit
	2. if (index == 0) then use deleteAtfirst() and exit
	3. if (index < 0 or index >= size) then throw IndexOutOfBoundsException and exit
	4. create a new Node temp1 and put it equal to **head**
	5. repeat substep for i = 0 to index -1
		1. traverse temp 1 to index - 1 or **temp = temp.next**
	6. create another Node temp2 and put it equal to temp1.next *(the node or the element which we are going to delete)* 
	7. print element to be deleted which is inside the temp2 we just created or **temp2.val**
	8. point temp1 to the element next to the temp2 or **temp1.next = temp2.next** *deletion step*
2. exit
#### Code to delete at certain index-
```java
public void deleteAtIndex(int index){  
    if (head == null){  
        System.out.println("List is empty");  
        return;  
    }  
    if(index == 0){  
        deleteAtFirst();  
        return;  
    }  
    if (index < 0 || index >= size) {  
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);  
    }  
    Node temp1 = head;  
    for (int i = 0; i <index - 1 ; i++) {  
        temp1 = temp1.next;  
    }  
    Node temp2 = temp1.next;  
    System.out.println("Element to be deleted: "+ temp2.val);  
    temp1.next =  temp2.next; //deletion  
	  
    if (temp2 == tail){  
        tail = temp1;  
    }    
    size--;  
}
```

### 7. Algo to get value at specified index and get size of the list
1. define method getIndex
	1. if index < 0 or index >= size then throw IndexOutOfBoundsException exception 
	2. create a new node obj in class Node
	3. repeat substep 1 for i = 0 to index 
		1. traverse node to the next node or node = node.next
	4. return value inside the node 
2. exit 
3. define method getSize
	1. return size
4. exit
#### Code to get the value at specified index and get size of the list-
```java
// Retrieves the value at a specific index (0-based indexing)  
// Time Complexity: O(n) in worst case   
// @param index - the position of the element to retrieve (0-based)    
// @return the value at the specified index    
// @throws IndexOutOfBoundsException if index is invalid    

public int getIndex(int index){  
	// Validate index bounds  
	if (index < 0 || index >= size) {  
		throw new IndexOutOfBoundsException("Index: " + index + ", Size: " +
		size);  
	}        
	// Traverse to the specified index  
	Node node = head;  
	for (int i = 0; i < index; i++) {  
		node = node.next;  
	}        
	return node.val;   
}  

// Returns the current size of the linked list  
// Time Complexity: O(1)    
// @return the number of elements in the list    

public int getSize() {  
	return size;  
}
```
---
[[Linked List]]