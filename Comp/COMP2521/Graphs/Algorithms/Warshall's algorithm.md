## Transitive closure matrix
A **transitive closure matrix** is a matrix that encodes if one node is reachable from another node. This is also called a **reachability matrix**.

## Warshall's algorithm
Warshall's algorithm relies on the concept that **If there is a path from A to B and a path from B to C then there is a path from A to C**.

```Pseudo
warshall(A):
	Input: n × n adjacency matrix A
	Output: n × n reachability matrix
	create tc matrix which is a copy of A
	for each vertex k in G: // from 0 to n - 1
		for each vertex s in G:
			for each vertex t in G:
				if tc[s][k] and tc[k][t]:
					tc[s][t] = true
	return tc
```

### Analysis
For Warshall's we get the following:
- Time complexity $O(V^3)$
- Space complexity  $O(V^2)$