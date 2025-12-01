## Motivation
At the moment our main ways of storing data is in **arrays** and **linked lists**. 
The key problem BSTs solve is **searching** for items in a large pool of data.

- To find data in a **linked list** we need to run through every node hence our worst case time complexity is $O(n)$.

- To find data in a **sorted array** we can employ a **binary search** reducing the time worst case time complexity to $O(\log n)$. *However*, insertion into a sorted array costs $O(n)$
## The BST
To solve the issue of insertion and searching that both **linked lists** and **sorted arrays** provide we modify the **linked list** so we can perform a binary search on it.

For every node of a **linked list** we attach *two* nodes, *left* and *right* where:
- every element in the *left* tree is less than the value of the current node
- every element in the *right* tree is greater than the value of the current node

A example struct is bellow
```C
struct bst {
	struct node *t;
}

struct node {
	int value;
	struct node *l;
	struct node *r;
}
```

An example of a BST is bellow
```
     4
    / \
   /   \
  2     6
 / \   / \
1   3 5   7
```
## Nomenclature
- The topmost node is called the <font color="46864F">root node</font>.
- Any node without any child nodes is called a <font color="46864F">leaf node</font>.
- Any node with at least one child node is called an <font color="46864F">internal node</font>
- The <font color="46864F">height</font> of a tree (h) is defined as the maximum number of edges between the root node and a leaf node.
	- Note an empty tree's height is -1.
- A tree is said to be <font color="46864F">balanced</font> if the height is minimal (h is close to $\lfloor{\log_2(n)}\rfloor$, and <font color="46864F">degenerate</font> if the height is maximal (h is close to n). There are two measures of a tree's balance:
	- **Size Balanced**: A tree is size-balanced if, for every node, the difference between the <font color="458CFF">sizes</font> of its  <font color="963CC9">left</font> and <font color="963CC9">right</font> <font color="46864F">subtrees</font> is less than or equal to 1. Or, $|\text{size}(l) - \text{size}(r)| \le 1$.
	- **Height Balanced**: A tree is height-balanced if, for every node, the difference between the <font color="458CFF">heights</font> of its  <font color="963CC9">left</font> and <font color="963CC9">right</font> <font color="46864F">subtrees</font> is less than or equal to 1. Or, $|\text{height}(l) - \text{height}(r)| \le 1$.
## Key operations
The following operations are key to base BSTs
### Insert
Inserting into a BST takes $O(h)$ time with the code bellow:
```C
void bstInsert(Bst tree, int item) {
	tree->t = doBstInsert(tree->t, item);
}

struct node *doBstInsert(struct node *t, int item) {
	if (t == NULL) return newNode(item);
	if (t->value == item) return t;
	
	if (item < t->value) t->l = doBstInsert(t->l, item);
	if (item > t->value) t->r = doBstInsert(t->r, item);
	return t;
}

struct node *newNode(item) {
	struct node *new = malloc(sizeof(struct node));
	new->value = item;
	new->l = NULL;
	new->r = NULL;
	return new;
}
```
### Search
Searching in a BST takes $O(h)$ time with the code bellow:
```C
void bstSearch(Bst tree, int key) {
	doBstSearch(tree->t, key);
}

void doBstSearch(struct node *t, int key) {
	if (t == NULL) {
		// Element was not in tree
	}
	if (t->value == key) {
		// You have found your node
	}
	
	if (key < t->value) doBstSearch(t->l, key);
	if (key > t->value) doBstSearch(t->r, key);
}
```
###  Traversal
Consult the page [[BST Traversal|here]]
### Join
Given two BSTs $t_1 \text{ and } t_2$ where $\max(t_1) < \min(t_2)$ return a BST containing all items from both trees
#### Overview
To join the two trees we are going to do the following:
- Find the minimum node in $t_2$
- Replace min with it's right sub tree
- elevate min to the root node
```C
Bst bstJoin(Bst t1, Bst t2) {
	if (t1->t == NULL) return t2;
	if (t2->t == NULL) return t1;
	if (t2->t->l == NULL) {
		t2->t->l = t1;
		return t2;
	}
	
	struct node *curr = t2->t;
	struct node *parent = NULL;
	while (curr->l != NULL) {
		parent = curr;
		curr = curr->l;
	}
	parent->l = curr->r;
	curr->left = t1->t;
	curr->right = t2->t;
	Bst new = newBst();
	new->t = curr;
	free(t1);
	free(t2);
	return new;
}

Bst newBst(void) {
	Bst new = malloc(sizeof(struct bst));
	new->t = NULL;
	return new;
}
```
#### Analysis
Joining takes $O(h_2)$ in the worst case
### Deletion
Deletion is a little more complex with the following code:
```C
void bstDelete(Bst tree, int item) {
	tree->t = doBstDelete(t);
}

struct node *doBstDelete(struct node *t, int item) {
	if (t == NULL) return t;
	if (item < t->value) t->l = doBstDelete(t->l, item);
	if (item > t->value) t->r = doBstDelete(t->r, item);
	// Found element to delete
	struct node *new;
	if (t->l == NULL) {
		new = t->r;
	} else if (t->r == NULL) {
		new = t->l;
	} else {
		new = bstJoin(t->l, t->r)
	}
	free(t);
	return new;
}
```
The above code as a time complexity of $O(h)$
## Pitfalls
Whilst BSTs promise $O(\log(n))$ time complexities, they are *only* able to reach this speed when the tree is balanced.

With base **BSTs** this behavior is not guaranteed and can even be effected by user input! To counteract this we can use the balancing operations found [[Balancing BSTs|here]] or use an **AVL tree** found [[AVL Trees |here]]
