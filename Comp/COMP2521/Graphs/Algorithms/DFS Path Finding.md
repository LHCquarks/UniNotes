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
## DFS path checking
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