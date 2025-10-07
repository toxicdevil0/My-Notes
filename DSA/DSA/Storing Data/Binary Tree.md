Binary Tree is just like Linked List, but instead of having next Node, it's gonna have left and right child Nodes.
And it's structure is also gonna look just like Linked List as well.

```java
class Node{
	int value;
	Node left;
	Node right;
}
```

#### Terms of Binary Tree-
1. Size - Total number of nodes
2. Child and Parent
3. Leaf Nodes - Nodes without any child nodes
4. Root Node - the first starting node
5. Siblings - if any nodes have the same parent, then they are siblings
6. Edge - Lines connecting two nodes 
7. Height - Max No. of edges btw the `x` node and the leaf node
8. Level - Difference of root node and the `x` node heights (root level = 0)

### Types Of Binary Tree-
1. Complete Binary Tree - Every level in the tree are filled except the last level and the last level full from Left → Right
   ![[Drawing 2025-10-05 01.36.11.excalidraw]]
2. Full or Strict Binary Tree - Every node has either zero or two child nodes
3. Perfect Binary Tree - All levels are full 
   ![[Drawing 2025-10-05 01.43.53.excalidraw]]
4. Height Balanced Binary Tree - Avg Height O(logN)
5. Skewed Binary Tree - Every node has only one child
6. Ordered Binary Tree - Nodes are stored in a certain order, like BST (Binary Search Tree - Left smaller or equal and Right bigger)
7. Degree - No. of child nodes (so it can be 0, 1, 2) {Highest degree in the tree is it's degree, like how degree in an exponential equation degree is the highest power of the variable}

