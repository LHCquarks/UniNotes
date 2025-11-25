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
## Building a component array
We can group our nodes into maximally connected sub graphs of the original graph with a component array.

A component array is simply an array with one int per vertex denoting which group it belongs to.

We can construct one of these arrays with a DFS were instead of a visited array we have our components array which is initialized to -1 and for every run of DFS we:
- set each node visited to our current group number in the component array
- increase the group number by 1
- find the next vertex in the graph who's component number is still -1
- run the grouping on them
### Uses
A component array is very useful for answering the following questions fast:
- How many components are there in this graph?
- Is there a path between these two vertexes?

### Maintaining a component array
When we add a edge to the graph we have to look at the two vertexes it connects and if they are apart of two groups we need to merge the groups

If we delete an edge we need to 

## Hamiltonian stuff
### Hamiltonian path
A Hamiltonian path is a path were we do not cross the same vertex more than once and visit every single vertex

To implement this we need to conduct a DFS on each vertex of the graph and if we are able to visit every node once then we return true.
To do this properly if a DFS fails then we need to set all it's nodes to not visited

Time complexity: $O(V!)$
### Hamiltonian cycle
A Hamiltonian cycle is a Hamiltonian path but the start and end vertex is the same

To find this we conduct a search for a Hamiltonian path but at the end check if the final node is adjacent to the first node.

Note that this time we do not have to loop through every vertex as if there is a cycle every vertex is apart of it
## Euler stuff
### Eulerian path
An Eulerian path is like a Hamiltonian path but this time we only care about the edges.
An Eulerian path is defined as a path that crosses every edge of a graph only once

Euler proved that an Eulerian path exists if and only if there are exactly 2 vertices that have an odd degree. These two vertices are then the start and end of the path.

Time complexity O(V+E)
### Eulerian Circuit
This is just an Eulerian path that ends on the same vertex.

Euler proved that an Eulerian path exists if and only if there are no vertices that have an odd degree.
## Weighted and directed graphs 
Usually graphs are directed and have some sense of cost associated with an edge
#### Nomenclature
We call directed graphs **digraphs**

We define the **In-degree** of a vertex to be the number of edges incoming to the vertex
We define the **Out-degree** of a vertex to be the number of edges outgoing from the vertex

A digraph is **strongly connected** if there is a path from each node to every other node

A **strongly connected component** is a maximally strongly connected sub graph
## Algorithms
Traversal:
- [[BFS]]
- [[DFS]]
Path finding:
- [[BFS Path Finding]]
- [[DFS Path Finding]]
Cycle checking:
- [[Cycle checking]]
Minimum spanning tree:
- [[Prims Algorithm]]
- [[Kruskals Algorithm]]