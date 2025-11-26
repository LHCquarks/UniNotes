Kruskals Algorithm is used to find a minimum spanning tree of a network.

Kruskals:
- Start with an empty graph
	- With same vertices as original graph
- Consider edges in increasing weight order
	- Add edge if it does not form a cycle in the MST
- Repeat until V − 1 edges have been added

The two main implementations are bellow:
### Removal
```Psudo
kruskalMst(G):
	Input: graph G with V vertices
	Output: minimum spanning tree of G
	
	mst = empty graph with V vertices
	sortedEdges = sort edges of G by weight
	for each edge e in sortedEdges:
		add e to mst
		if mst has a cycle:
			remove e from mst
		if mst has V − 1 edges:
			return mst
```
### Path checking
```Psudo
kruskalMst(G):
	Input: graph G with V vertices
	Output: minimum spanning tree of G
	
	mst = empty graph with V vertices
	sortedEdges = sort edges of G by weight
	for each edge (v, w, weight) in sortedEdges:
		if there is no path between v and w in mst:
			add edge (v, w, weight) to mst
		if mst has V − 1 edges:
			return mst
```
## Analysis
Using Cycle / Path checking with an adjacency list  is $O(E\log E + EV) = O(EV)$

Using Cycle / Path checking with an adjacency list  is $O(E\log E + E) = O(E\log E)$