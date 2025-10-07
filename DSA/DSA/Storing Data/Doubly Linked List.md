It's basically just like singly linked list but a node has access to both the previous and the next nodes
![[Drawing 2025-08-16 00.45.47.excalidraw | 580]]

## 1. Inserting at first 
1. create a new node
2. point node's next to start
3. and node's previous pointer to null
4. if (start != null) then start.prev = node
5. put start = node

![[Drawing 2025-08-17 00.51.23.excalidraw | 580]]
### Code-
```java
public void insertAtFirst(int val){  
    Node node = new Node(val);  
    node.next = head;  
    node.prev = null; //when inserting for the first time  
	  
    if(head != null){  
        head.prev = node;  
    }    head = node;  
}
```
## 2. Inserting at given number
1. get index for where to insert
2. initialize a node p to start or p = start
3. traverse node p to the index - 1 by p = p.next
4. create new node to be inserted
5. if(p.next  == null) then insertion at last and exit
6. point node's next to p's next
7. point p's next to node
8. point node's prev to p
9. point node's next's previous (to access p's next) to node
![[Drawing 2025-08-16 01.07.12.excalidraw | 580]]
### Code-
```java
public void insertionAtIndex(int index, int val){  
        if(index == 0){  
            insertAtFirst(val);  
            return;  
        }  
        Node p = head;  
        for (int i = 0; i <index -1 ; i++) {  
            if (p == null){  
                throw new IndexOutOfBoundsException("Index too large");  
            }            p = p.next;  
        }  
        if (p == null){  
            throw new IndexOutOfBoundsException("Invalid too large");  
        }  
		  
        if(p.next == null){  
            //checking if inserting at last  
            insertionAtLast(val);  
            return;  
        }  
        Node node = new Node(val);  
        node.next = p.next;  
        p.next = node;  
        node.prev = p;  
        node.next.prev = node;  
    }
}
```
---
[[Linked List]]
