There are 4 main ways to traverse a BST:

The first **3** perform depth first traversals where the order that the node was operated on differentiates them

| Traversal   | Order (Left Node Right) |
| ----------- | ----------------------- |
| In-order    | LNR                     |
| Pre-order   | NLR                     |
| Post-order  | LRN                     |
| Level-order | Layer by layer          |
## In-order
In order traversal visits each node in numerical order. Code is bellow:
```C
void inOrderTraversal(Bst t) {
	doInOrderTraversal(t->t);
}

void doInOrderTraversal(struct node *t) {
	doInOrderTraversal(t->l);
	// Do something with the current node
	doInOrderTraversal(t->r);
}
```
## Pre-order
Pre order traversal visits the parent node **before** exploring the child nodes. Code is bellow:
```C
void preOrderTraversal(Bst t) {
	doInOrderTraversal(t->t);
}

void doPreOrderTraversal(struct node *t) {
	// Do something with the current node
	doInOrderTraversal(t->l);
	doInOrderTraversal(t->r);
}
```
## Post-order
Post order traversal visits the parent node **after** exploring the child nodes. Code is bellow:
```C
void postOrderTraversal(Bst t) {
	doInOrderTraversal(t->t);
}

void doPostOrderTraversal(struct node *t) {
	doInOrderTraversal(t->l);
	doInOrderTraversal(t->r);
	// Do something with the current node
}
```
## Level-order
Level order traversal visits all the nodes in one level before exploring any nodes from lower levels. Code is bellow:
```C
void levelOrderTraversal(Bst t) {
	Queue q = queueNew();
	queueEnqueue(q, t->t);
	while (!queueIsEmpty(q)) {
		struct node *curr = queueDequeue(q);
		queueEnqueue(q, curr->l);
		queueEnqueue(q, curr->r);
		// Do something
	}
}
```