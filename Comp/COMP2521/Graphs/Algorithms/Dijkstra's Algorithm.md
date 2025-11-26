Dijkstra's algorithm finds the **shortest path** in a **weighted graph** with non-negative weights.

Dijkstra's algorithm explores from the src edge going to the next unvisited edge in the graph with the smallest distance from the src node. At each edge it enacts **edge relaxation** where it updates the distances of neighbouring nodes by considering paths through the current node.

## Data structures
Dijkstra's uses a:
- Distance array (int array with size of number of nodes)
- Predecessor array (int array with size of number of nodes)
- Set of vertices
## Edge Relaxation
Suppose we have the nodes A, B and C in a triangle with edges:
- A -> B: 10
- A -> C: 4
- C -> B: 4
On our first iteration we find that out dist array looks like `[0, 10, 4]`. When we then move onto inspecting C we are able to find a path from C -> B such that A -> C + C -> B < 10. This then allows us to **relax** B's distance to 4 + 4 = 8 giving us the dist array `[0, 8, 4]`.

## Psudo
Bellow is the psudo code for Dijkstra's algorithm:
```Psudo
dijkstraSSSP(G, src):
	Input: graph G, source vertex src
	
	create dist array, initialised to ∞
	create pred array, initialised to -1
	create vSet containing all vertices of G
	
	dist[src] = 0
	while vSet is not empty:
		find vertex v in vSet such that dist[v] is minimal
		remove v from vSet
		for each edge (v, w, weight) in G:
			relax along (v, w weight)
```
This gives a predecessor array that encodes the shortest path from the src node to any other node.

## Analysis
Dijkstra's algorithm's time complexity depends on it's implementation details especially for the vertex set. Bellow are time complexities for various set implementations:
- Visited array - $O(E + V^2) = O(V^2)$
- Array of vertices - $O(E + V^2) = O(V^2)$
- Priority queue - $O(E + V\log V)$