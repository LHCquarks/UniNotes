BFS finds the shortest path between the starting vertex and all other vertices in terms of the **number of edges**. By tracing through the predecessor array starting from `dest`, the shortest path from `dest` to `src` can be found. A stack can be used in conjunction with this method to find the path from `src` to `dest`.

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