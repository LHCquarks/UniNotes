We start with a DFS and if it reaches a node that is already in the visited array then we have a cycle:
```C
hasCycle(G):    
	Input: graph G
	
	pick any vertex v in G
	create visited array, initialised to false
	dfsRecHasCycle(G, v, v, visited)
	
dfsRecHasCycle(G, v, prev, visited):
	Input: Graph G, vertex v, vertex previous vertex, visited array
	
	visited[v] = true
	for each neighbour w of v in G that is not prev:
		if visited[w] = false:
			dfsRec(G, v, visited)
		else:
			return true
```
Note this does not check if the cycle is only 2 nodes. 
To fix this we keep track of the previous vertex:
```C
hasCycle(G):    
	Input: graph G
	
	pick any vertex v in G
	create visited array, initialised to false
	return dfsRecHasCycle(G, v, v, visited)
	
dfsRecHasCycle(G, v, prev, visited):
	Input: Graph G, vertex v, vertex previous vertex, visited array
	
	visited[v] = true
	for each neighbour w of v in G:
		if w == prev:
			continue
		if visited[w] == true:
			return true
		if dfsRecHasCycle(G, w, v, visited):
			return true
		else:
			return false
```
Note if our graph is disconnected this does not find all cycles
To solve this we will simply run this again until we have searched every vertex:
```C
hasCycle(G):    
	Input: graph G
	
	pick any vertex v in G
	create visited array, initialised to false
	for each vertex v of G:
		if visited[v] == true
			continue
		if dfsRecHasCycle(G, v, v, visited)
			return true
	
dfsRecHasCycle(G, v, prev, visited):
	Input: Graph G, vertex v, vertex previous vertex, visited array
	
	visited[v] = true
	for each neighbour w of v in G:
		if w == prev:
			continue
		if visited[w] == true:
			return true
		if dfsRecHasCycle(G, w, v, visited):
			return true
		else:
			return false
```