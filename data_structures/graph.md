# Graph

A graph is a data structure composed of vertices and edges. Say you have a piece of paper and you draw something. The points where two lines connect is a vertex, the lines connecting the vertices are the edges. A graph is denoted by $G(V, E)$, where $G$ is the graph, $E$ are the edges and $V$ are the vertices.

> Note: Vertices are also called nodes. Edges are also called arcs.

A graph is used to represent complex relationships between objects. For example: in a social network, every user is a vertex and edges are the relationships between users; in a map, roads are vertices and intersections are vertices.

## Storing a graph

Graphs can be stored in two ways. An adjacency matrix or an adjacency list/graph.

### Adjacency matrix

An adjacency matrix is a 2D matrix where rows and columns denote vertices. If the value at $G[i][j]$ is non-zero, there's an edge connecting the vertices $i$ and $j$ with weight $G[i][j]$. Else, there's no edge connecting them.

### Adjacency list/graph

An adjacency list is a list of linked lists denoting where there are edges. For every vertex $v$, there's a linked list containing all elements it is connected to with an edge.

## Types of graphs

Some of the many types of graphs. Many types may apply to a graph at the same time.

For example, trees are a specific type of graph: connected and acyclic graphs that have a root node and a unique path between two vertices.

**Null graph**: A graph with no edges.

**Trivial graph**: A graph with a single vertex, the smallest graph possible.

**Undirected graph**: A graph in which edges do not have direction (e.g. you can travel back and forth through edges).

**Directed graph**: A graph in which edges have direction (e.g you can only travel forward through edges).

**Connected graph**: A graph in which all nodes are connected directly or indirectly, meaning there's a path in the graph from any node A to another node B.

**Disconnected graph**: A graph in which not all nodes can be reached from any other node.

**Regular graph**: A graph in which all vertices have K edges connecting to them is called a K-regular graph.

**Complete graph**: A graph in which all nodes are connected to each other, where there is an edge connecting any node A to any other node B.

**Cycle graph**: A graph that is a cycle in itself; a 2-regular graph.

**Cyclic graph**: A graph that contains at least one cycle.

**Weighted graph**: A graph in which edges have a value associated to them (a weight). For example, in a map a road will have a length.

**Bipartite graph**: A graph in which the vertices can be divided into two sets such that the vertices on each set have no edges connecting them within their set.