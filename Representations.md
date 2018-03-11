#### Representations

QuickGraph provides various data structures that can represent directed/undirect dense/sparse graphs. All data structures are serializable, cloneable and **not** thread safe. Graphs are mutable or immutable (immutable graphs usually have a more compact representation). The delegate based graphs can be used to keep the memory consumption low.

* Directed graphs
	* [AdjacencyGraph](AdjacencyGraph.md) provides access to vertices, edges and out edges of sparse directed graphs.
	* [BidirectionalGraph](BidirectionalGraph.md) extends AdjacencyGraph by providing access to in edges but it requires the double of memory space.
	* [BidirectionalMatrixGraph](BidirectionalMatrixGraph.md) represented by an array. Efficient for dense directed graphs with known number of vertices.
	* [ArrayAdjacencyGraph](ArrayAdjacencyGraph.md) and [ArrayBidirectionalGraph](ArrayBidirectionalGraph.md) are readonly equivalent of [AdjacencyGraph](AdjacencyGraph.md) and [BidirectionalGraph](BidirectionalGraph.md). They also use slightly less memory.
	* [CompressedSparseRowGraph](CompressedSparseRowGraph.md) is an adjacency graph using a compact representation called [compressed sparse row](http://www.cs.utk.edu/~dongarra/etemplates/node373.html.md). Only the vertex can be of custom type.
	* [DelegateImplicitGraph](DelegateImplicitGraph.md) wraps the [IImplicitGraph](IImplicitGraph.md) interface on top of a delegate that a vertex to a set of out vertices. This representation is efficient for large graph that cannot be stored in memory at once 
	* [DelegateIncidenceGraph](DelegateIncidenceGraph.md) wraps the [IIncidenceGraph](IIncidenceGraph.md) interface, and extends [DelegateImplicitGraph](DelegateImplicitGraph.md)
	* [DelegateVertexAndEdgeListGraph](DelegateVertexAndEdgeListGraph.md) wraps the [IVertexAndEdgeListGraph](IVertexAndEdgeListGraph.md), extends the DelegateIncidenceGraph, and also uses an enumeration for the vertices
* Undirected graphs
	* [UndirectedGraph](UndirectedGraph.md) provides a representation for sparse undirected graphs.
* Adapters
	* [BidirectionalAdapterGraph](BidirectionalAdapterGraph.md) wraps an adjacency graph into a [bidirectional graph](BidirectionalGraph.md) (access to in-edges)
	* [UndirectedBidirectionalGraph](UndirectedBidirectionalGraph.md) wraps a bidirectional graph into a [undirected graph](UndirectedGraph.md).