Prims Algorithm is used to find a minimum spanning tree of a network.

Prims:
- Start with an empty graph
- Start from any vertex and add it to the MST
- Chose Cheapest edge s-t such that:
	- s has been added to the MST
	- t has not been added to the MST
	- Add this edge to MST
- Repeat until V − 1 edges have been added

The two main implementations are bellow:
## Implementation
```Psudo
primMst(G):
	Input: graph G with V vertices
	Output: minimum spanning tree of G
	
	mst = empty graph with V vertices
	usedV = {0}
	unusedE = edges of G
	while |usedV| < V:
		find cheapest edge e (s, t, weight) in unusedE such that
			s ∈ usedV and t ∈/ usedV
		add e to mst
		add t to usedV
		remove e from unusedE
	return mst
```
## Analysis
Using a set of vertices is $O(E\log E + EV) = O(EV)$

Using Fibonacci heap is $O(E + V\log V)$
