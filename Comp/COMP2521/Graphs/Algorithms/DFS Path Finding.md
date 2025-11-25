## DFS Path Finding
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