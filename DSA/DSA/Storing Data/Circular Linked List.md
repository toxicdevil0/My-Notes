A Circular Linked List is a variation of a linked list where the last node points back to the first node (head), creating a circular structure. This circularity allows traversal to continue indefinitely without reaching a null reference.

![[Drawing 2025-09-06 02.46.16.excalidraw | 680]]
## Types of Circular Linked Lists

### 1. Circular Singly Linked List
In a circular singly linked list, each node has a reference to the next node, and the last node points back to the first node.

### 2. Circular Doubly Linked List
In a circular doubly linked list, each node has references to both the next and previous nodes. The last node's next points to the first node, and the first node's previous points to the last node.

## Implementation of Circular Singly Linked List

In a circular linked list, the nodes are similar to those in a singly linked list, but the organization ensures there is no null termination.

```java
public class CircularLinkedList {
    
    private Node head;
    private Node tail;
    private int size;
    
    // Node class definition
    private class Node {
        private int val;
        private Node next;
        
        public Node(int val) {
            this.val = val;
        }
        
        public Node(int val, Node next) {
            this.val = val;
            this.next = next;
        }
    }
    
    // Constructor
    public CircularLinkedList() {
        this.size = 0;
    }
}
```

---

### Operations on Circular Linked List

#### 1. Algo for inserting at the head
1. Define method insertAtFirst
   2. Create a new node with the given value
   3. If list is empty (head == null)
      1. Set head and tail to the new node
      2. Point the node's next to itself (creating a circle)
   4. If list is not empty
      1. Point the new node to the current head
      2. Update the tail's next to point to the new node (maintain the circle)
      3. Update head to the new node
   5. Increment size by 1
6. Exit

##### Code for inserting at the head
```java
// Inserts a new node at the beginning of the circular list
// Time Complexity: O(1)
// @param val - the value to insert
public void insertAtFirst(int val) {
    Node node = new Node(val);
    
    if (head == null) {
        head = node;
        tail = node;
        node.next = node; // Points to itself in a single-node circular list
    } else {
        node.next = head;
        tail.next = node; // The last node must point to the new head
        head = node;
    }
    
    size++;
}
```

---

#### 2. Algo for inserting at the tail
1. Define method insertAtLast
   2. Create a new node with the given value
   3. If list is empty (head == null)
      1. Use insertAtFirst and exit
   4. If list is not empty
      1. Point the new node to the head (to maintain the circle)
      2. Point tail's next to the new node
      3. Update tail to the new node
   5. Increment size by 1
6. Exit

##### Code for inserting at the tail
```java
// Inserts a new node at the end of the circular list
// Time Complexity: O(1) - thanks to tail pointer
// @param val - the value to insert
public void insertAtLast(int val) {
    // If list is empty, use insertAtFirst method
    if (head == null) {
        insertAtFirst(val);
        return;
    }
    
    Node node = new Node(val);
    
    // In a circular list, the new last node points back to head
    node.next = head;
    tail.next = node;
    tail = node;
    
    size++;
}
```

---

#### 3. Algo for displaying the elements
1. Define method display
   2. If list is empty (head == null), print "List is empty" and exit
   3. Create a temporary node and set it to head
   4. Do-While loop (to ensure at least one iteration for circular lists)
      1. Print the value in the temporary node
      2. Move to the next node
      3. Continue until returning to head
   5. Print "HEAD" to indicate completion of the circle
6. Exit

##### Code for displaying the elements
```java
// Displays all elements in the circular list
// Time Complexity: O(n) where n is the number of elements
public void display() {
    if (head == null) {
        System.out.println("List is empty");
        return;
    }
    
    Node temp = head;
    do {
        System.out.print(temp.val + " -> ");
        temp = temp.next;
    } while (temp != head);
    
    System.out.println("HEAD"); // Indicates we've completed the circle
}
```

---

#### 4. Algo for deleting at the head
1. Define method deleteAtFirst
   2. If list is empty (head == null), print "List is empty" and exit
   3. Print element to be deleted (head.val)
   4. If only one element in list (head == tail)
      1. Set head and tail to null
   5. Otherwise
      1. Update head to head.next
      2. Update tail.next to the new head (maintain the circle)
   6. Decrement size by 1
7. Exit

##### Code for deleting at the head
```java
// Deletes the first node from the circular list
// Time Complexity: O(1)
public void deleteAtFirst() {
    // Check if list is empty
    if (head == null) {
        System.out.println("List is empty");
        return;
    }
    
    System.out.println("Element to be deleted: " + head.val);
    
    // If only one element in the list
    if (head == tail) {
        head = null;
        tail = null;
    } else {
        head = head.next;
        tail.next = head; // Update the last node to point to the new head
    }
    
    size--;
}
```

---

#### 5. Algo for deleting at the tail
1. Define method deleteAtLast
   2. If list is empty (head == null), print "List is empty" and exit
   3. If only one element (head == tail), use deleteAtFirst and exit
   4. Create a temporary node starting at head
   5. Traverse to the node before tail
      1. While temp.next != tail, update temp = temp.next
   6. Print element to be deleted (tail.val)
   7. Update tail to be the node before current tail (temp)
   8. Update tail.next to point to head (maintain the circle)
   9. Decrement size by 1
10. Exit

##### Code for deleting at the tail
```java
// Deletes the last node from the circular list
// Time Complexity: O(n) - needs to traverse to second-to-last node
public void deleteAtLast() {
    // Check if list is empty
    if (head == null) {
        System.out.println("List is empty");
        return;
    }
    
    // If only one element in the list
    if (head == tail) {
        deleteAtFirst();
        return;
    }
    
    Node temp = head;
    // Traverse to the node before tail
    while (temp.next != tail) {
        temp = temp.next;
    }
    
    System.out.println("Element to be deleted: " + tail.val);
    
    // Update tail and maintain the circle
    tail = temp;
    tail.next = head;
    
    size--;
}
```

---

#### 6. Algo for inserting at a specific index
1. Define method insertAtIndex
   2. If index < 0 or index > size, throw IndexOutOfBoundsException
   3. If index == 0, use insertAtFirst and exit
   4. If index == size, use insertAtLast and exit
   5. Create a temporary node pointing to head
   6. Traverse to the node at position (index-1)
   7. Create a new node with the given value
   8. Connect the new node to the list:
      1. Point new node's next to temp's next
      2. Point temp's next to the new node
   9. Increment size by 1
10. Exit

##### Code for inserting at a specific index
```java
// Inserts a new node at the specified index in the circular list
// Time Complexity: O(n) in worst case
// @param index - the position to insert the new element (0-based)
// @param val - the value to insert
public void insertAtIndex(int index, int val) {
    if (index < 0 || index > size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    
    if (index == 0) {
        insertAtFirst(val);
        return;
    }
    
    if (index == size) {
        insertAtLast(val);
        return;
    }
    
    Node temp = head;
    for (int i = 0; i < index - 1; i++) {
        temp = temp.next;
    }
    
    Node node = new Node(val, temp.next);
    temp.next = node;
    
    size++;
}
```

---

#### 7. Algo for deleting at a specific index
1. Define method deleteAtIndex
   2. If list is empty (head == null), print "List is empty" and exit
   3. If index == 0, use deleteAtFirst and exit
   4. If index == size-1, use deleteAtLast and exit
   5. If index < 0 or index >= size, throw IndexOutOfBoundsException
   6. Create a temporary node pointing to head
   7. Traverse to the node at position (index-1)
   8. Store the node to be deleted (temp.next) in a variable
   9. Print element to be deleted
   10. Update temp's next to skip the deleted node (temp.next = temp.next.next)
   11. Decrement size by 1
12. Exit

##### Code for deleting at a specific index
```java
// Deletes the node at the specified index in the circular list
// Time Complexity: O(n) in worst case
// @param index - the position of the element to delete (0-based)
public void deleteAtIndex(int index) {
    if (head == null) {
        System.out.println("List is empty");
        return;
    }
    
    if (index == 0) {
        deleteAtFirst();
        return;
    }
    
    if (index == size - 1) {
        deleteAtLast();
        return;
    }
    
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    
    Node temp = head;
    for (int i = 0; i < index - 1; i++) {
        temp = temp.next;
    }
    
    Node toDelete = temp.next;
    System.out.println("Element to be deleted: " + toDelete.val);
    
    temp.next = toDelete.next;
    size--;
}
```

---

#### 8. Algo for searching a value
1. Define method search
   2. If list is empty (head == null), return -1 (not found)
   3. Create a temporary node pointing to head
   4. Initialize index to 0
   5. Do-While loop (for circular list)
      1. If temp's value matches the search value, return the index
      2. Increment index and move to the next node
      3. Continue until returning to head
   6. Return -1 if value not found
7. Exit

##### Code for searching a value
```java
// Searches for the first occurrence of a value in the circular list
// Time Complexity: O(n) where n is the number of elements
// @param value - the value to search for
// @return the index of the value if found, -1 otherwise
public int search(int value) {
    if (head == null) {
        return -1; // Not found in empty list
    }
    
    Node temp = head;
    int index = 0;
    
    do {
        if (temp.val == value) {
            return index; // Value found
        }
        temp = temp.next;
        index++;
    } while (temp != head);
    
    return -1; // Value not found
}
```

---

#### 9. Utility methods
```java
// Returns the current size of the circular linked list
// Time Complexity: O(1)
// @return the number of elements in the list
public int getSize() {
    return size;
}

// Checks if the circular list is empty
// Time Complexity: O(1)
// @return true if the list is empty, false otherwise
public boolean isEmpty() {
    return head == null;
}
```

## Advantages of Circular Linked Lists

1. **Continuous traversal**: We can traverse the entire list starting from any node.
2. **No null checks**: Since there are no null ends, certain operations can be simpler.
3. **Efficient for applications** that require repeated traversals around a collection (like round-robin scheduling).
4. **Implementation of circular buffers**: Ideal for implementing circular buffers or queues.

## Applications of Circular Linked Lists

1. **Round-robin scheduling** in operating systems
2. **Circular buffers** in embedded systems
3. **Turn-based multiplayer games**
4. **Audio/Video streaming** buffers
5. **Implementation of advanced data structures** like Fibonacci Heaps

## Circular Doubly Linked List

A circular doubly linked list combines the features of both circular and doubly linked lists. Each node has both next and previous pointers, and the list forms a circle in both directions.

This structure allows for even more flexibility in traversal, as you can move both forwards and backwards without encountering null references.

The implementation is similar to regular doubly linked lists, with the addition that the last node's next points to the first node, and the first node's previous points to the last node.