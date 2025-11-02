## Overview
- AVL Trees are Binary Search Trees which are always height-balanced. 
- A tree is 'repaired' locally as soon as an imbalance occurs (insertion and deletion).
- An AVL tree does not need to be size-balanced. The tree below is a perfectly valid AVL tree:
```      
         10
        /  \
       /    \
      /      \
     4        15
    / \        \
   /   \        \
  2     6        16
 / \   / \
1   3 5   7
```

- **Trivia:** The name 'AVL' comes from the names of the inventors: Georgy <font color="EB8E7F">A</font>delson-<font color="EB8E7F">V</font>elsky and Evgenii <font color="EB8E7F">L</font>andis
## Implementation
### Insertion
 AVL Trees are easiest implemented recursively:
- Insert Item Recursively
- Check and fix imbalances in reverse (from bottom to top - after recursive call)

```c
struct node *newNode(int v) {
	struct node *newNode = malloc(sizeof(struct node));
	newNode->item = v;
	newNode->left = NULL;
	newNode->right = NULL;
	newNode->size = 1;
	newNode->height = 1;
	return newNode;
}

struct node *avlInsert(struct node *t, int v) {
	if (t->size == 0) {
		return newNode(val);
	} else if (v < t->item) {
		t->left = avlInsert(t->left, val);
		t->left->size++;
	} else if (v > t->item) {
		t->right = avlInsert(t->right, val);
		t->left->size++;
	} else {
		return t;
	}
	t->height = maxSize(t->left, t->right) + 1;
	return avlRebalance(t); 
}

struct node *avlRebalance(struct node *t) {
	if (balance(t) > 1) {
		if (balance(t->left) < 0) {
			t->left = rotateLeft(t->left);
		}
		t = rotateRight(t);
	} else if (balance(t) < -1) {
		if (balance(t->right) > 0) {
			t->right = rotateRight(t->right);	
		}
		t = rotateLeft(t);
	}
	return t;
}

int balance(struct node *t) {
	return t->left->height - t->right->height;
}

```

Looking at the rebalancing function, there are 4 rebalancing cases:
- Left Left
- Left Right
- Right Left
- Right Right

Storing the height of a subtree in the struct node requires maintenance upon insertion and deletion. Heights of each subtree is recalculated in reverse, using the heights of their children.

#### Complexity Analysis
Like any other binary search tree, the worst-case time complexity of insertion is $O(h)$. However, AVL trees are always balanced, meaning $h=log(n)$. So, the worst-case time complexity of insertion is $O(log(n))$. The same is true for searching.

What about deletion?

### Deletion
Deletion follows the same method as insertion:
- Delete Item recursively
- Check and fix balance in reverse (after the recursive call)

```c
avlDelete(struct node *t, int v) {
	if (t->size == 0) {
		return t;
	} else if (v < t->item) {
		t->left = avlDelete(t->left, v);
	} else if (v > t->item) {
		t->right = avlDelete(t->right, v);
	} else {
		if (t->left->size == 0) {
			temp = t->right;
			free(t);
			return temp;
		} else if (t->right->size ==0) {
			temp = t->left;
			free(t);
			return temp;
		} else {
			successor = minimum value in t->right;
			t->item = successor;
			t->right = avlDelete(t->right, successor);
		}
	}
	return avlRebalance(t);
}
```


These notes are pretty basic. For a better understanding on AVL trees, refer to other sources.