# Trees
- A tree is like a linked list, but with more than one next node.
- Types of trees might be binary (2 next nodes), ternary (3 next nodes) and so one
# Binary Search Trees
- Binary: 2 Next Nodes (left and right)
- Search: Going left returns smaller data, going right returns larger data (Fundamental Property of a Binary Search Tree)
- Example:
```
     4
    / \
   /   \
  2     6
 / \   / \
1   3 5   7
```
## Properties
- The topmost node is called the <font color="46864F">root node</font>.
- Any node without any child nodes is called a <font color="46864F">leaf node</font>.
- The <font color="46864F">height</font> of a tree (h) is defined as the maximum number of edges between the root node and a lead node.  So, the height of the tree above is 2. Following this logic, 
	- A tree with only one node (the root) has a height of 0.
	- An empty tree's height is -1.

- A tree is said to be <font color="46864F">balanced</font> if the height is minimal (h is close to log(n), and <font color="46864F">degenerate</font> if the height is maximal (h is close to n). There are two measures of a tree's balance:
	- **Size Balanced**: A tree is size-balanced if, for every node, the difference between the <font color="458CFF">sizes</font> of its  <font color="963CC9">left</font> and <font color="963CC9">right</font> <font color="46864F">subtrees</font> is less than or equal to 1. Or, $|size(l) - size(r) \le 1|$.
	- **Height Balanced**: A tree is height-balanced if, for every node, the difference between the <font color="458CFF">heights</font> of its  <font color="963CC9">left</font> and <font color="963CC9">right</font> <font color="46864F">subtrees</font> is less than or equal to 1. Or, $|height(l) - height(r) \le 1|$.
	
- If the order of inputted values is increasing, the tree is called <font color="46864F">right-heavy</font>.
- If the order of inputted values is decreasing, the tree is called <font color="46864F">left-heavy</font>

```
1             |            4
 \            |           /
  2           |          3
   \          |         / 
    3         |        2 
     \        |       /
      4       |      1
This tree is  |   This tree is
right-heavy   |   left-heavy 

Both trees have a height of 3 and are degenerate.
```
## Traversal
- In-Order: Only read node when the nodes subtrees have been read. Start with the left, then right. (LRN) (Read node when you reach the bottom)
- Pre-Order: Read node, then left node and all its subtrees, then right node and all its subtrees (subtrees are traversed the same way) (NLR) (Left)
- Post-Order Traversal: Read node then right node and its subtrees, left node and its subtrees, and then node.(Right)
- Level-Order: Read the nodes in levels (Node, left, right, ..)

Right-Heavy Trees have the same Pre-Order and In-Order Traversal

Trees with one value or empty trees have the same traversal no matter what method used.


A node might look like this:
```c
struct node {
    int data,
    struct node *left,
    struct node *right
}
```

## Complexity Analysis
The structure of binary search trees (and the property of a smaller nodes being inserted to the left and larger nodes to the right) means that insertion, deletion, and searching for a node has worst-case time complexity $O(h)$, where $h$ is the height of the tree. If a tree is balanced, this is close to $O(log(n))$, because every time the algorithm traverses to the next level, the number of possible nodes halves.

If a tree is unbalanced, or degenerate, this time complexity becomes $O(n)$, which is not very efficient. Balancing a binary search tree allows this to be avoided.
## Balancing BSTs
Balancing a tree is done through <font color="963CC9">rotations</font> about nodes. 
### Left and Right Rotations
Rotating about node `n` changes the subtree whose root is `n`, whilst still maintaining the fundamental property of a binary search tree.
- **Left Rotation** (about node `n`):
	- The subtree's `newRoot` is `n->right`
	- `n->right` is set to `newRoot->left
	- `newRoot->left` is set to `n`
	- `newRoot` is returned
-  **Right Rotation** (about node `n`):
	- The subtree's `newRoot` is `n->left
	- `n->left` is set to `newRoot->right`
	- `newRoot->right is set to `n`
	- `newRoot` is returned

![[BST Rotations.png]]

#### Implementation of BST Rotation
```c
struct node *rotateRight(struct node *root) {
	if (root == NULL || root->left == NULL) return root;
	struct node *newRoot = root->left;
	root->left = newRoot->right;
	newRoot->right = root;
	return newRoot;
}
struct node *rotateLeft(struct node *root) {
	if (root == NULL || root->right == NULL) return root;
	struct node *newRoot = root->right;
	root->right = newRoot->left;
	newRoot->left = root;
	return newRoot;
}
```
**Complexity Analysis**: Worst-Case Time Complexity is $O(1)$ 
### Partitioning
- Partitioning a node is the process of rotating the tree until it becomes the parent. 
- Partitioning is usually done by index rather than value (where elements in the tree are indexed starting from `0` in the order of the tree's in-order traversal)
- The simplified process is as follows:
	- Find element with index `i`
	- While the element is not the root:
		- If it is the left child of its parent, perform a right rotation at its parent
		- If it is the right child of its parent, perform a left rotation at its parent
- Keeping track of the parent can be difficult. The method used is to keep track of the size of each node's subtree with a `size` field in the struct. Since the indices are assigned in-order, the index of a node is the same as the number of elements in the tree which are less than it's value.

#### Implementation of a Partition Function
Partitioning is easiest done recursively:
```c
struct node *partition(struct node *t, int i) {
	if (i < t->left->size) {
		t->left = partition(t->left, i);
		t = rotateRight(t);
	} else if (i > t->left->size) {
		t->right = partition(t->right, i - t->left->size - 1);
		t = rotateLeft(t);
	}
	return t;
}
```
**Complexity Analysis**: Worst-Case Time Complexity: $O(log(n))$
### Rebalancing a Tree
There are two methods of rebalancing a tree:
- **Global Rebalancing**
	- Visit every node and rebalance its subtree (costly)
- **Local Rebalancing**
	- Rebalance small subtrees of a BST with efficient, localised algorithms (imperfect balance)

#### Global Rebalancing
- Lift the median node to the root(index $\lfloor size(t)/2 \rfloor$, using integer division to floor)
- Rebalance both of its subtrees

**Problems**
- Rebalancing Trees can be costly. It's not ideal to rebalance a tree on every insert, so how often? Every `k` inserts?
- However often we insert, it's a tradeoff. The most ideal solution is specific to each use-case.
###### Global Rebalancing Implementation
```c
struct node *rebalance(struct node *t) {
	if (t->size < 3) {
		return t;
	}

	t = partition(t, t->size / 2);
	t->left = rebalance(t->left);
	t->right = rebalance(t->right);
	return t;
}
```

**Complexity Analysis**: The time complexity of each partition is $O(nlog(n))$. Each partition step is $O(log(n))$, and this must happen $n$ times (one for each node).

#### Local Rebalancing

<font color="19FF27">Root Insertion</font> and <font color="19FF27">Randomised Insertion</font> are two local rebalancing methods. 

Root Insertion inserts a node normally, then partitions around that node, and is more likely to be balanced. It also means recent data is closer to the root, and is faster to access. The problem with root insertion is that if data is inserted in order, it is still worst-case.

Randomised Insertion chooses randomly whether to insert at the root of the leaf. This was, ascending or descending order inputs are more likely to be balanced.

##### Root and Random Insert Implementation

```c
struct node *insertAtRoot(struct node *t, int v){
	if (t->size == 0) {
		return newNode(v);
	} else if (v < t->item) {
		t->left = insertAtRoot(t->left, v);
		t = rotateRight(t);
	} else if (v > t->item) {
		t->right = insertAtRoot(t->right, v);
		t = rotateLeft(t);
	}
	return t;
}

struct node *insertRandom(struct node *t, int v){
	if (t->size == 0) {
		return newNode(v);
	}	
	// p/q chance of inserting at root
	if (random() mod q < p) {
		return insertAtRoot(t, v);
	} else {
		return insertAtLeaf(t, v);
	}
}

struct node *newNode(int v) {
	struct node *newNode = malloc(sizeof(struct node));
	newNode->item = v;
	newNode->left = NULL;
	newNode->right = NULL;
	newNode->size = 1;
	return newNode;
}
```

[[AVL Trees]] are types of Binary Search Tree with auto-height balancing upon insertion and deletion, which are performed locally. This allows them to be efficient and the tree is height-balanced (Time complexity for Insertion and Deletion is $O(log(n))$)