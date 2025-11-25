**Breadth first search** first searches the closest nodes then the further out nodes.

## Implementation
We use a **queue** to keep track of the nodes to visit, a visited array to keep track of the nodes we have already visited and a predecessor array to keep track of the found paths.

Breadth-First-Search visits vertices in order of distance from the starting vertex in terms of the number of edges. It is implemented iteratively using a queue.
```C
void bfs(Graph G,int src) {
	bool *visited = create_visited_array(G);
	int *predecessor = create_predecessor_array(G);
	Queue q = QueueNew();
	
	visited[src] = true;
	QueueEnqueue(q, src);
	
	while (!QueueEmpty(q)) {
		int v = QueueDequeue(q);
		int num_neighbours = GraphGetNumNeighbours(G, v);
		int *neighbours = malloc(sizeof(int) * num_neighbours);
		GraphGetNeighbours(G, v, neighbours);
		for (int i = 0; i < num_neighbours; i++) {
			int w = neighbours[i];
			if (visited[w]) continue;
			visited[w] = true;
			predecessor[w] = v;
			QueueEnqueue(q, w);
		}
	}
}

bool *create_visited_array(Graph G) {
	bool *visited = malloc(Graph_size(G) * sizeof(bool));
	for (int i = 0; i < Graph_size(G); i++) {
		visited[i] = false;
	}
	return visited;
}

int *create_predecessor_array(Graph G) {
	bool *pred = malloc(Graph_size(G) * sizeof(int));
	for (int i = 0; i < Graph_size(G); i++) {
		pred[i] = -1;
	}
	return pred;
}
```
### Analysis
The time complexity of BFS depends on the graph implementation used:
- For the adjacency list representation, is it O(V + E) since:
    - Queue implementation has O(1) create, enqueue and dequeue, and O(V) or O(1) clear
    - Each vertex is visited at most once -> O(V)
    - For each vertex, all edges are considered once -> O(E)