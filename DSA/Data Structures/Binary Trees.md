Binary Tree is  non-linear data structure where each node has at most two children.
It is a tree data structure (non-linear) in which each node can have at most two children. These are referred to as **left child** and **right child**.

The topmost node is called the root. The bottom-most nodes are called leaves. A binary tree can be visualised as a hierarchical structure with the rot at the top and the leaves at the bottom.

## Representation of Binary Tree
Each node has three parts:
- Data
- Pointer to the left child
- Pointer to the right child

![[Binary-Tree-Representation.webp]]

## Terminology
- **Nodes**: fundamental part of a binary tree, where each ode contains data and link two child nodes
- **Root**: The topmost node in a tree. It has no parent and serves as the starting point for al the nodes on a tree.
- **Parent Node**: a node that has one or more child nodes. Each node can have at most two children nodes
- **Child Node**: a node that is descendant of another node
- **Leaf Node**: a node that does not have any children
- **Internal Node**: a node that has at least one child. This includes all nodes except for the root and leaf nodes.
- **Depth of Binary Tree**: the number of edges from a specific node to the root node.
- **Height of a Binary Tree**: the number of nodes from the deepest leaf node to the root node.


![[Terminologies-in-Binary-Tree-in-Data-Structure_1.webp]]

## Properties
- maximum no. of nodes at level L is `2^L`
- maximum number of nodes in a binary tree of height H is `2^h - 1`
- total number of leaf nodes is `total no. of nodes with 2 children + 1`
- in binary tree with N nodes, minimum possible height or the minimum no. of levels is `log2(N+1)`
- a binary tree with L leaves has at least `|Log2L| + 1`  levels

## Coding Example
**Java** 
Code example of a node of a circular linked list and creating binary tree with four nodes:

``` java
// class containing left and right child of current node and key value

class Node {
	int data;
	Node left, right;
	
	public Node(int item) {
		data = item;
		left = right = null;
	}
}

class GfG {
	public static main(String[] args) {
	//initialize and allocate memory for tree nodes
		Node firstNode = new Node(2);
		Node secondNode = new Node(3);
		Node thridNode = new Node(4);
		Node fourthNode = new Node(5);

	// connect binary tree
		firstNode.left = secondNode;
		firstNode.right = thirdNode;
		secondnode.left = fourthNode;
	}
}
```

**Python**

``` python
# class that represents an individual node in a bianry tree
class Node:
	def __init__(self, key) {
		self.left = None
		self.right = None
		self.val = key
	}

# initialie and allocate memory
firstNode = Node(2)
secondNode = Node(3)
thirdNode = Node(4)
fourthNode = Node(5)

# connect binary trees
firstNode.left = secondNode
firstNode.right = thirdNode
secondNode.left = fourthNode
```

In the above code, we have created four tree nodes, **firstNode, secondNode** and **fourthNode**. 

- Connect the ****secondNode**** to the left of ****firstNode**** by ****firstNode->left = secondNode****
- Connect the ****thirdNode**** to the right of ****firstNode**** by ****firstNode->right = thirdNode****
- Connect the ****fourthNode**** to the left of ****secondNode**** by ****secondNode->left = fourthNode***


