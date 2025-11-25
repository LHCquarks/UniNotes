Depth First Search goes as far down one path as possible until it reaches a dead end, then backtracks until it finds a new path to take, and repeats.

DFS can be implemented iteratively using a stack, or recursively.
### Iterative Implementation
```Pseudo code 
dfs(G, src):
	Input: graph G, vertex src
	
	create visited array, initialised to false
	create predecessor array, initialised to -1
	create stack S
	
	push src onto S
	
	while S is not empty:
		v = pop from S
		if visited[v] = true:
			continue
		
		visited[v] = true
		
		for each neighbour w of v in G where visited[w] = false:
			predecessor[w] = v
			push w onto S
```

### Recursive Implementation
```Pseudo code
dfs(G, src):    
	Input: graph G, starting vertex src
	
	create visited array, initialised to false
	dfsRec(G, src, visited)
	
dfsRec(G, v, visited):
	Input: Graph G, vertex v, visited array
	
	visited[v] = true
	for each neighbour w of v in G:
		if visited[w] = false:
			dfsRec(G, v, visited)
```

### Analysis
Recursive and Iterative DFS are both O(V + E) when using the adjacency list representation:
- Recursive DFS:
    - Each vertex is visited at most once -> O(V)
        - Function is called on each vertex at most once
    - For each vertex, all of its edges are considered once -> O(E)
- Iterative DFS:
    - Typical stack implementation has O(1) push and pop
    - Each vertex visited at most once -> O(V)
    - For each vertex, all of its edges are considered -> O(E)
## Connected components
To find all the connected components of a graph we perform repeated DFS searches until we have visited all the nodes in the graph.

We switch out our visited array for a group array initialized to -1 and perform DFS on node $0$. Every node we visit we set its respective element in the group array to be $0$. 

We then find the next node which has not been visited and apply DFS on that setting the group element to be $1$ this time. This pattern continues until we have visited every node.

Now every node of every component has the same number and we can easily tell if two nodes are reachable from one another