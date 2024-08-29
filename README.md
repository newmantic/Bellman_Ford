# Bellman_Ford


The Bellman-Ford algorithm is used to find the shortest paths from a single source vertex to all other vertices in a weighted graph. It can handle graphs with negative weight edges, but it cannot handle graphs with negative weight cycles.

Input: A directed graph G = (V, E) where:
V = set of vertices
E = set of edges, with weights w(u, v) for each edge (u, v).

Output: The shortest path distances from the source vertex src to all other vertices. If a negative weight cycle is detected, the algorithm will report it.



Initialization:
Create an array dist of size |V| to store the shortest distances from the source.
Initialize all distances as ∞ (infinity), except for the source vertex:
dist[src] = 0 // Distance to itself is zero.

Relaxation:
For each vertex, repeat the following process |V| - 1 times:
For each edge (u, v) with weight w(u, v):
If dist[u] + w(u, v) < dist[v], then update:
dist[v] = dist[u] + w(u, v)
This step relaxes the edge, meaning it checks if the shortest known distance to vertex v can be improved by taking the edge from u to v.

Check for Negative Weight Cycles:
After |V| - 1 iterations, perform one more iteration over all edges:
For each edge (u, v) with weight w(u, v):
If dist[u] + w(u, v) < dist[v], then a negative weight cycle exists.
Raise an error or return a message indicating that a negative weight cycle is present.

Time Complexity:
The time complexity of the Bellman-Ford algorithm is O(V * E), where V is the number of vertices and E is the number of edges. This is due to the |V| - 1 relaxation steps for all edges.

The algorithm can handle negative weights but not negative cycles.
It is less efficient than Dijkstra's algorithm for graphs without negative weights but is more versatile due to its ability to handle negative weights.
