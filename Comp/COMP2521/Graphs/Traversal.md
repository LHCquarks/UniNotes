
There are two main ways to traverse a graph:
- **Breadth-First-Search**:
	- First searches all the closest nodes and then the further out nodes
	- Uses a Queue to keep track of which nodes to explore (and the order)
	- Generalization of level order traversal in BSTs
- **Depth-First-Search**:
	- Searches entire paths before moving onto another path
	- Uses a Stack to keep track of which nodes to explore (and the order)
	
The pseudo code for each implementation method is the same.
## DFS Path Checking
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

