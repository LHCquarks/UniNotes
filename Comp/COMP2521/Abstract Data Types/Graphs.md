## Overview
A graph is a series of nodes which are each connected to an arbitrary number of nodes. It is a more general data structure than linked lists and trees. Graphs are useful for maps, websites, social networks, circuits, networking, game states, and so on.

A graph contains:
- A set of V vertices (also called nodes)
- A set of E edges between pairs of vertices.

Vertices are usually distinguished by a unique identifier (usually between 0 and V -1).

Edges can be (but aren't always) directed, weighted and/or labelled

## Terminology
### Graph Terminology
Graphs can be:
- **Undirected** or **Directed** (Do edges have direction?)
- **Unweighted** or **Weighted** (Do edges have an associated scalar weight?)
- **Without loops** or **with loops** (Can an edge start and end at the same vertex?)
- **Non-multigraph** or **multigraph** (Can multiple edges connect a single pair of nodes?)
- **Connected** or **Disconnected** (Can the graph be separated into multiple parts)

A **simple** graph is a type of graph which is:
- Undirected
- Without loops
- Non-multigraph

A **complete graph** is a graph where every vertex is connected to every other vertex via an edge. In a complete graph, E = `V(V-1)/2`

### Vertex Terminology:
- **Adjacent** vertices have an edge connecting them
- If an edge `e` connects two vertices `v` and `w`, it is **incident** upon them 
- The **degree** of a vertex is the number of edges which are incident on it.
### Sparsity:
The E:V ratio of a graph tells us about its sparsity:
- If E is close to V^2, the graph is **dense**
- If E is close to V, the graph is **sparse**
### Paths
A path is a sequence of vertices connected by edges.
- A **simple** path has no repeating vertices
- A **cycle** is a type of path where only the first and last vertices are the same
## Graph Properties
- A **tree** is a connected graph with no cycles
- A **subgraph** of a graph G is a graph which contains a subset of the vertices of G and a subset of the edges between these vertices
- A **connected component** is a maximally connected subgraph
- A **spanning tree** of a graph G is a subgraph which contains all vertices of G and a single tree
- A **spanning forest** of a graph G is a subgraph containing all vertices of G and a single tree for each connected component
- A **clique** is a complete subgraph

## Implementation
There are three common implementation methods of a Graph ADT:
- **Adjacency Matrix**: Two-dimensional array of bools or ints indicating the presence of, and weight of adjacent nodes of each node.
- **Adjacency List**: Array of linked lists containing the adjacent nodes of each node
- **Array of Adjacent Pairs**: Array, where every entry contains two nodes (and a weight) indicating the edge between these nodes.
## Traversal
There are two main ways to traverse a graph:
- **Breadth-First-Search**:
	- First searches all the closest nodes and then the further out nodes
	- Uses a Queue to keep track of which nodes to explore (and the order)
	- Generalization of level order traversal in BSTs
- **Depth-First-Search**:
	- Searches entire paths before moving onto another path
	- Uses a Stack to keep track of which nodes to explore (and the order)
	
The pseudo code for each implementation method is the same.
### Breadth-First-Search (BFS)
Breadth-First-Search visits vertices in order of distance from the starting vertex in terms of the number of edges. It is implemented iteratively using a queue.
```Pseudo code
bfs(G,src)
	Input: graph G, starting vertex src
	
	create visited array, initialised to false
	create predecessor array, initialised to -1
	create queue Q
	
	visited[src] = true;
	enqueue src into Q
	
	while Q is not empty
		v = dequeue from Q
		for each neighbour of w of v in G such that visited[w] = false
			visited[w] = true
			predecessor[w] = v
			enqueue w into Q
```
#### Analysis

The time complexity of BFS depends on the graph implementation used:
- For the adjacency list representation, is it O(V + E) since:
    - Queue implementation has O(1) create, enqueue and dequeue, and O(V) or O(1) clear
    - Each vertex is visited at most once -> O(V)
    - For each vertex, all edges are considered once -> O(E)

### BFS Path Finding
BFS finds the shortest path between the starting vertex and all other vertices in terms of the number of edges. By tracing through the predecessor array starting from `dest`, the shortest path from `dest` to `src` can be found. A stack can be used in conjunction with this method to find the path from `src` to `dest`.

```Pseudo code
bfsPathFind(G, src, dest):    
	Input: graph G, vertices src and dest
	
	... BFS starting from src ...
	
	if predeessor[dest] != -1
		v = dest
		while v != src
			print v, "<-"
			v = predecessor[v]
		print src
```

### Depth-First-Search
Depth First Search goes as far down one path as possible until it reaches a dead end, then backtracks until it funds a new path to take, and repeats.

DFS can be implemented iteratively using a stack, or recursively.
#### Iterative Implementation
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

#### Recursive Implementation
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

#### Analysis
Recursive and Iterative DFS are both O(V + E) when using the adjacency list representation:
- Recursive DFS:
    - Each vertex is visited at most once -> O(V)
        - Function is called on each vertex at most once
    - For each vertex, all of its edges are considered once -> O(E)
- Iterative DFS:
    - Typical stack implementation has O(1) push and pop
    - Each vertex visited at most once -> O(V)
    - For each vertex, all of its edges are considered -> O(E)
### DFS Path Checking
- Depth First Search is helpful for checking if a path is present, especially when the nodes being checked are far away from each other. 
```Pseudo code
dfsHasPath(G, src, dest)
	Input: graph G, vertices src and dest
	Output: true is there is a path from src to dest false otherwise
	
	create visited array, initialised to false
	return dfsHasPathRec(G, src, dest, visited)

dfsHasPathRec(G, v, dest, visited)
	Input: graph G, vertices v and dest, visited array
	
	visited[v] = true
	if v = dest:
		return true
		
	for each neighbour w of v in G:
		if visited[w] = false:
			if dfsHasPathRec(G, w, dest, visited);
				return true
	
	return false
```

### DFS Path Finding
```Pseudo code
dfsFindPath(G, src, dest)
	InputL graph G, vertices src and dest
	
	create predecessor array, initialised to -1
	predecessor[src] = src
	
	if dfsFindRathRec(G, src, dest, predecessor):
		v = dest
		while v != src:
			print v, "<-"
			v = predecessor[v]
			
		print src

dfsFindPathRec(G, v, dest, predecessor);
	if v = dest:
		return true
		
	for each neighbour w of v in G:
		if predecessor[w] = -1:
			-redecessor[w] = v
			if dfsFindPathRec(G, w, dest, predecessor):
				return true
				
	return false
```
