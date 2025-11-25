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